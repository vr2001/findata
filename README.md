# Charts to Watch V2

A separate Streamlit application based on your original Charts to Watch code. Your original application remains unchanged.

## What's new

- **FRED economic section removed completely** (no FRED API key needed).
- Clearer navigation: Ratio Dashboard, Performance, Fundamentals, Technicals, Cheat Sheet.
- More welcoming layout, with the ratio inputs in the page itself and a collapsible advanced-options panel.
- Fix for a ratio-chart bug where changing the tickers without rerunning the chart could trigger a mismatch in the saved price columns.
- Performance comparison now normalizes every ticker from its own first available closing price rather than relying on all tickers having values on the first shared date.
- Other existing research features retained, including CSV downloads.

## Run a new copy locally (Windows)

1. Extract this ZIP into a **new folder** (e.g. `Documents\\charts_to_watch_v2`). Do **not** overwrite your existing app folder.
2. Open Anaconda Prompt or Windows Terminal in that new folder.
3. Install the dependencies:

   ```powershell
   python -m pip install -r requirements.txt
   ```

4. Launch the new app on a different port, so it can run beside your original:

   ```powershell
   python -m streamlit run app.py --server.port 8502
   ```

5. Go to **http://localhost:8502** in your browser. This is a *local* second app; publishing it online is a separate step.

## Publish as a separate website

1. Create a **new GitHub repository**, e.g. `charts-to-watch-v2` (keep your existing repository untouched).
2. Upload `app.py` and `requirements.txt` from this ZIP to the new repository.
3. In [Streamlit Community Cloud](https://share.streamlit.io/), click **Create app**, choose the new repository, set the main file path to `app.py`, and deploy.
4. Streamlit will give your second application its own URL. Check the app's availability and data outputs after deployment.

## Important limitations

- Yahoo Finance data is unofficial and can be delayed, missing, rate-limited, or changed.
- Technicals, fundamentals and valuation figures are research aids, not independently verified market data.
- Existing valuation calculations (including historical EV/EBITDA) are approximate and should be independently checked. Historical shares outstanding and filing timing can materially affect the result.
- This version was **syntax-checked**, but could not be fully run against live Yahoo data in the current environment. Test each page locally before publishing.
