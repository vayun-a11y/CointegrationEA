# CointegrationEA

New H1 bar?
├── Update Kalman β (hedge ratio)
├── Every 24 bars: Run ADF test → still cointegrated?
├── Every 24 bars: Calculate half-life → still mean-reverting fast enough?
├── Check ADX → market ranging, not trending?
├── If any filter fails → close all positions immediately
├── If all good → calculate current Z-score
    ├── Z > +2.0 and no position → short the spread
    ├── Z < -2.0 and no position → long the spread
    └── |Z| < 0.5 and position open → close everything
