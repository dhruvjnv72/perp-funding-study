# Perp Funding Study

Perpl settles funding about every 43 minutes. What would traders have paid if funding accrued every block instead? This study measures the difference on real Perpl data.

**Status: in progress, started October 2026.** There are no results yet. Nothing here is a finding.

## The question

On Perpl, funding is applied at fixed intervals (about 8,571 blocks, roughly 43 minutes). Some designs update funding continuously. Using Perpl's own history, how different would the amounts be under:

1. the current discrete schedule, and
2. a per-block accrual of the same rate?

and does the difference matter more for some markets, position sizes or holding times?

## Planned method

- **Funding history:** decode the exchange's funding events from chain logs.
- **Prices:** Perpl's public candle API.
- **Positions:** representative holdings (for example a 1-hour and a 6-hour position at fixed size), not real traders.
- Compare total funding paid or received under each schedule, and show the gap per market.
- A small Solidity reference contract for a per-block cumulative funding index, with unit tests, to show the mechanism.

## Milestones

- [ ] Project skeleton, decoder for funding events
- [ ] Price and funding dataset for the available window
- [ ] Discrete-schedule calculation
- [ ] Per-block accrual calculation
- [ ] Comparison tables and plots
- [ ] Reference funding-index contract with tests
- [ ] Write-up with limits

## Honest limits

- Only the window of history we can decode is analysed; short windows can mislead.
- It uses representative positions, not what real traders actually held.
- It measures a mechanism. It does not claim that either design is better.

## License

MIT, see [LICENSE](LICENSE).
