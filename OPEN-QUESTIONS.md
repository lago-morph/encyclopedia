# Open modeling questions

Honest list. Each gets resolved by a decision node, not by silent drift.

1. **Decision-node maturity.** Do decisions ride the L0-L3 ladder or only a
   status lifecycle (proposed/adopted/superseded)? Currently: status only,
   maturity fixed at L0. Revisit when the linter forces the question.
2. **component vs work-item boundary.** Components are things the system IS;
   work-items are endeavor (things we DO). Boundary cases will appear.
3. **Expression language** for machine-checkable criteria beyond "a script
   exits 0" — the known hardest problem (see dec-0004 provenance). Deferred
   until the gate-kit slice demands it.
4. **Per-kind state cards.** dec-0008 adopts the form; the first card exists
   (schema/state-cards/component.yaml) but is unenforced until the linter
   binds its rule ids. Grow per kind, on demand.
5. **serves-edge reach.** Must every node trace to a jtbd, or only certain
   kinds? Currently enforced for: component, contract, work-item, initiative, plan.
6. **Concrete node-identity rules.** dec-0009 adopts the principle; the
   actual same-node-vs-new-node tests and granularity guidance are undesigned.
