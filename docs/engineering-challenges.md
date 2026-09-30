# Engineering Challenges

## Reliable Timing With Unstable Connectivity

**Problem**  
Connectivity can be unreliable during a live competition.

**Decision**  
Let operators keep working even when the API is temporarily unreachable.

**Solution**  
Use local Android persistence, pending synchronisation and physical tickets.

**Outcome**  
The field workflow is more resilient to temporary network failures.

## Fast Finish-Line Capture

**Problem**  
At the finish line, the timestamp can be available before the operator can comfortably enter the race number.

**Decision**  
Separate timestamp capture from race-number assignment.

**Solution**  
Allow operators to capture one or more pending times and assign race numbers afterwards.

**Outcome**  
The operator can prioritise capturing the time at the correct moment.

## Safe Corrections

**Problem**  
Timing records may need corrections during an event.

**Decision**  
Avoid treating corrections as simple destructive overwrites.

**Solution**  
Use logical record versioning and keep a current version for result calculations.

**Outcome**  
Corrections can be reflected in the public results while preserving a safer operational model.

## Physical Input Devices

**Problem**  
Touch interaction is not always ideal at a timing checkpoint.

**Decision**  
Support external button/pedal-like input.

**Solution**  
Handle mouse-style events with debounce logic in the Android workflow.

**Outcome**  
The app adapts better to field timing hardware.

## Hill Climb To Rally

**Problem**  
Rally adds stages, runs, checkpoints, ideal times and accumulated classifications.

**Decision**  
Introduce Rally-specific concepts rather than overloading the simpler Hill Climb model.

**Solution**  
Model itinerary points, stage runs, control records, neutralisations and Rally classifications.

**Outcome**  
The product supports a richer motorsport domain.

## Participant Imports

**Problem**  
Updating participant lists should not accidentally destroy existing sporting data.

**Decision**  
Make participant updates safer and keep deletion explicit.

**Solution**  
Update entries by race number and separate destructive removal into its own operation.

**Outcome**  
Race administration becomes safer during event preparation.

## Rally Stage Closure

**Problem**  
At stage closure, some competitors may have missing start or finish records.

**Decision**  
Apply consistent sporting states based on the records available.

**Solution**  
Treat missing starts and missing finishes differently, while preserving competitors that already have a finish record.

**Outcome**  
Race control can close operational gaps without manually resolving every case from scratch.
