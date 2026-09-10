# Blackbox Native Resolution

Blackbox is a native-first resolution and control layer for BlackRoad.

It separates five concerns that are often incorrectly collapsed into one:

1. **Observation**: what was actually seen.
2. **Evidence**: what supports or contradicts a claim.
3. **Resolution**: what conclusion is currently justified.
4. **Authority**: what a principal is permitted to do.
5. **Capacity**: what the machine can safely afford to do.

The control plane is intentionally small and deterministic. Core utilities should prefer `/bin/zsh` and canonical system binaries over Python, Node, or model-generated control logic.

## Core axioms

- Observe before explaining.
- Retrieve before generating.
- Search rank is not evidence.
- Repetition is not corroboration.
- Product name is not instance identity.
- Authentication is not authorization.
- Reachability is not usability.
- Belief is not permission to act.
- Resource scarcity changes execution permission, not evidentiary conclusions.
- Conflicting evidence remains visible.
- Unknown remains unknown.
- Paths are boundaries, not locations.

## Boundaries

- `00`: root-local / private
- `01`: authorized egress
- `10`: untrusted ingress
- `11`: scoped shared state

No `00 -> 01` transition is implicit. No `10 -> 00` transition is trusted without verification. `11` is always scoped by principal, owner, project, or agent.

## Resolution flow

```text
QUERY
  -> classify domain
  -> determine burden
  -> identify evidence classes
  -> resolve source lineage
  -> compare context
  -> preserve contradictions
  -> assess coverage
  -> produce revisable resolution
  -> independently evaluate action authority
```

## Native-first rule

A model may reason over retrieved evidence, but models do not define machine state. When live machine observation conflicts with generated explanation, preserve the observation and discard the explanation.
