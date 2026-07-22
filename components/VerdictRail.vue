<script setup>
// The deck's spine: a PreToolUse hook returns exactly one of three verdicts.
// Every hook slide lights the one it is teaching, so people always know
// where they are in the arc.
//
//   <VerdictRail active="deny" />
//   <VerdictRail active="ask" done="deny" />
//   <VerdictRail active="deny,ask,allow" />

defineProps({
  active: { type: String, default: '' },
  done: { type: String, default: '' },
})

const VERDICTS = [
  { key: 'deny', verdict: 'DENY', label: 'Stop the call. Hand the model a reason.' },
  { key: 'ask', verdict: 'ASK', label: 'Pause and put a human in the loop.' },
  { key: 'allow', verdict: 'OBSERVE', label: 'Let it run — and write it down.' },
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
