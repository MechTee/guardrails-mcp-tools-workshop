<script setup>
// The deck's spine: an OpenCode `tool.execute.*` hook can do exactly three
// things to a pending tool call. Every plugin slide lights the one it is
// teaching, so people always know where they are in the arc.
//
//   <VerdictRail active="deny" />
//   <VerdictRail active="rewrite" done="deny" />
//   <VerdictRail active="deny,rewrite,observe" />
//
// "ask" is deliberately absent: in OpenCode that verdict lives in the
// declarative `permission` config, not in a plugin. See the Ex1 slide on it.

defineProps({
  active: { type: String, default: '' },
  done: { type: String, default: '' },
})

const VERDICTS = [
  { key: 'deny', verdict: 'DENY', label: 'Throw. The call never runs.' },
  { key: 'rewrite', verdict: 'REWRITE', label: 'Mutate the args. Sanitize, don\'t refuse.' },
  { key: 'observe', verdict: 'OBSERVE', label: 'Let it run — and write it down.' },
]

function has(list, key) {
  return String(list || '')
    .split(',')
    .map((s) => s.trim())
    .includes(key)
}
</script>

<template>
  <div class="rail">
    <div
      v-for="v in VERDICTS"
      :key="v.key"
      class="rail-item"
      :class="[
        `rail-item--${v.key}`,
        { 'is-active': has(active, v.key), 'is-done': has(done, v.key) },
      ]"
    >
      <span class="rail-verdict">{{ v.verdict }}</span>
      <span class="rail-label">{{ v.label }}</span>
    </div>
  </div>
</template>
