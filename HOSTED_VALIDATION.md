# NFL hosted validation — 2026-10-24

Live app: https://nfl-statistical-research.streamlit.app/

Repository: https://github.com/Pokered03/NFL-Statistical-Research

The user approved public visibility for this NFL project. The existing Multi-Sport Value Engine was not changed. This is a deployed development build; the complete requested specification is not finished.

## Checks completed

- Deployed main/app.py on Streamlit Community Cloud with Python 3.12.15.
- The real public hosted page renders its controls, team comparisons and prepared data.
- Empty scheduled date Oct 24 reports no games and suggests nearby dates. Oct 25 lists 12 scheduled matchups. Pittsburgh–New Orleans and Indianapolis–Minnesota comparisons rendered.
- Manual team comparison, team searches, 2025/2026 season switching, neutral/home venue changes, last 3/5/10 windows and source/validation expanders worked in the hosted browser.
- A second browser tab loaded independently while the first comparison session remained active. This is a basic concurrency check, not a load test.
- Live memory panel observed peak web-process RSS **161.5 MiB**; exposed cgroup memory limit **3072 MiB**; container usage **854.8–862.2 MiB**. Container usage includes other processes and file cache. The sampled app process is below the 350 MiB development target and the observed host limit. Long-term peaks remain unverified.
- Streamlit replaced PyArrow 26 after flagging it as a known segfault version. This NFL repository now pins **pyarrow==24.0.0**, matching the host. All **36 tests passed**, with 5 unrelated sport cases skipped, after the dependency and memory-panel change (1.86 seconds locally).
- Hosted refresh run https://github.com/Pokered03/NFL-Statistical-Research/actions/runs/40112680464 **succeeded in 41 seconds** (job 36 seconds), including tests, active-season collection, integrity validation and data publication. The live page picked up the resulting **2026-10-24T16:41:27.565541+00:00** update timestamp.

## Automatic updates and costs

Daily cron is **10:17 UTC**, subject to GitHub scheduling delays. ENABLE_FREE_REFRESH=true is set. Jobs also require a public repository and use only the standard ubuntu-latest runner. No cache or artifact storage is used. No paid APIs, Odds API credits, paid hosting or larger paid runners are configured. This is a daily schedule, not immediate end-of-game updating. GitHub may suspend inactive public schedules; monitor successful timestamps.

GitHub runner policy verified: https://docs.github.com/en/actions/how-tos/write-workflows/choose-where-workflows-run/choose-the-runner-for-a-job — standard GitHub-hosted runners are free for public repositories.

The successful workflow reported a non-blocking Node20 action deprecation warning (checkout@v4/setup-python@v5 forced to Node24) and an ubuntu-latest image migration notice. Review runner/action version updates as maintenance.

## Outstanding verification and research

- Real iPhone/mobile layout and MacBook-specific testing; sustained multi-user load, forced restart recovery and longer hosted soak tests.
- Reliable live injury/availability inputs and remaining unsupported advanced metrics. Keep these N/A.
- Additional model development and independent out-of-sample evaluation. Historical spread and total gates failed, so both remain PASS; do not infer trustworthy confidence from a running deployment.
- The other five dashboards remain independent local development builds at their earlier saved checkpoint and are not yet deployed.

**No claim of full completion: only this NFL deployment and its initial hosted checks are complete.**
