# nyc-subway-flood-check

A web-based decision tool that helps NYC subway riders understand whether a specific subway line is affected by flooding right now and how likely flooding is to disrupt their trip in the next 30–45 minutes during heavy rainfall.

This project is designed as decision support, not a navigation or forecasting app. It prioritizes clarity, transparency, and explainability over false precision.

### Problem Statement

During extreme rainfall events in New York City:
- Subway flooding often begins before official service alerts are issued
- Riders are forced to make travel decisions with fragmented or delayed information
- Existing tools focus on system-wide status, not trip-specific risk

Riders need a fast, honest answer to a simple question:

>"If I take this subway line right now, am I likely to get stuck — or should I wait or reroute?”

### What This Product Does

For a selected subway line (and direction), the tool provides:

1. **Current status (now)**: Whether flooding is reported or confirmed at the moment of search
2. **Near‑future flood risk (next 30–45 minutes)**: An evaluation of whether flooding is likely to emerge or worsen during the trip window
3. **Plain‑language explanation**: Why the system reached this assessment
4. **Suggested actions**: Practical guidance (wait, reroute, proceed with caution)

Results are presented as a single, mobile‑friendly result card designed for use during active weather.

### What This Product Does NOT Claim

To remain accurate and responsible, this project explicitly does not claim:
- Exact flood timing (e.g. “flooding will occur at 8:42 PM”)
- Exact underground flood boundaries
- Guaranteed safety or passability of any route
- Perfect real‑time knowledge during extreme events

All risk assessments are conditional and probabilistic, not deterministic.

### Data Layers & Roles

The system integrates multiple public data sources, each with a specific role:

#### Base (Always‑On Signals)

- Rainfall intensity (real time) – measures current stress on drainage systems
- Subway geometry – underground vs elevated segments

#### Risk Modifiers
- Historical flood vulnerability – stations/segments that have flooded in past storms
- Elevation & drainage context – relative ability to absorb or shed water

#### Confirmation Signals
- NYC 311 flooding complaints – near‑real‑time surface drainage failure
- User self‑reports – underground conditions experienced by riders
- MTA service alerts – official acknowledgment of service disruption

Each layer is weighted differently based on timeliness and certainty. No single dataset determines the result.

### Decision Logic (High Level)

The system follows a transparent, rule‑based evaluation:
- **Current status** is determined by confirmation signals (user reports, 311 complaints, MTA alerts)
- **Near‑future** risk is evaluated using rainfall intensity, short‑term rainfall trends, infrastructure exposure, and historical vulnerability

Risk is expressed using qualitative levels:
- Low
- Moderate
- Elevated
- High

No exact probabilities are shown to users.

### User Interface

The primary interface is a result card, not a map.

Each result card includes:
- Trip context (line + direction)
- Current status (now)
- Flood risk during the next 30–45 minutes
- A short explanation (“Why am I seeing this?”)
- Suggested actions

Maps exist only as a secondary explainer for pitching, transparency, and post‑event analysis.

### Intended Use Cases
- A rider deciding whether to leave work during a cloudburst
- Someone already en route checking if conditions are deteriorating
- Journalists, researchers, or planners examining how flooding risk evolves during storms

### Limitations & Biases
- NYC 311 complaints depend on reporting behavior and may underrepresent some neighborhoods
- User reports may be sparse at launch
- Radar‑based rainfall estimates have spatial uncertainty
- Underground flooding cannot be directly observed in real time

These limitations are surfaced transparently in the product’s methods documentation.

### Why This Exists

Extreme weather is becoming more frequent, but real‑time public information about infrastructure failure has not kept pace. This project explores how public data, environmental signals, and transparent logic can help people make better decisions during climate‑driven disruptions — without overpromising certainty.
