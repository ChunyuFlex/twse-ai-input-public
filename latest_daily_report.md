# 每日台股大盤 AI Input 更新

- 產生時間：2026-08-13 22:25:44
- 執行環境：GitHub Actions / Python 3.12.13

## 1. 今日更新結果
- Update TAIEX OHLC CSV：成功，exit code 0
- Update TWSE market context：成功，exit code 0
- Update TAIFEX derivatives：成功，exit code 0
- Build TWSE AI input：成功，exit code 0
- Build options OI summary：成功，exit code 0
- Generate AI article：失敗，exit code 2

## 2. 最新資料日期
- TAIEX OHLC：2026-08-13
- Market context row date：2026-08-13
- Market context latest institutional date：2026-08-13
- Market context latest breadth date：2026-08-13
- TAIFEX derivatives：2026-07-09

## 3. 程式判定摘要
- 現貨狀態：IN｜從DN回到通道內第10天
- 現貨動作：等回測
- 下一步：等待：UP新突破且StartBreakoutPct>0.36%→追
- 衍生性商品偏向：cautious
- 衍生性商品風險：medium_high

## 4. 更新檔案
- `twse/taiex_ohlc_amount_daily.csv`：2026-08-13 22:23:54，376,306 bytes
- `twse/twse_market_context_daily.csv`：2026-08-13 22:24:40，1,115 bytes
- `twse/twse_market_context_summary.csv`：2026-08-13 22:24:40，1,293 bytes
- `twse/taifex_derivatives_daily.csv`：2026-08-13 22:25:42，7,829 bytes
- `twse/taifex_options_oi_latest.csv`：2026-08-13 22:23:30，133,010 bytes
- `twse/AI_MODEL_INPUT/01_latest_signal.json`：2026-08-13 22:25:44，1,319 bytes
- `twse/AI_MODEL_INPUT/09_market_context_daily.csv`：2026-08-13 22:24:40，1,115 bytes
- `twse/AI_MODEL_INPUT/10_market_context_summary.csv`：2026-08-13 22:24:40，1,293 bytes
- `twse/AI_MODEL_INPUT/13_derivatives_signal_summary.json`：2026-08-13 22:25:44，1,025 bytes
- `twse/AI_MODEL_INPUT/15_options_oi_summary.json`：2026-08-13 22:25:44，1,998 bytes
- `twse/AI_MODEL_INPUT/14_ai_writer_prompt.md`：2026-08-13 22:25:44，1,913 bytes

## 5. 失敗輸出
### Generate AI article
```text
OPENAI_API_KEY is not configured. Set it in GitHub repository Settings > Secrets and variables > Actions > Repository secrets.
```

## 6. AI 自動產生文章

OPENAI_API_KEY is not configured. Set it in GitHub repository Settings > Secrets and variables > Actions > Repository secrets.

## 7. 備用提示詞

以下僅作為備用。正常情況下，本 workflow 已經自動產生上方文章，不需要手動貼給 GPT。

```markdown
# 台股盤勢分析稿產生指令

請根據本資料夾內的 CSV/JSON，產生一篇「類似財經新聞，但有明確分析判斷」的台股盤勢分析。

## 寫作原則

1. 不要只是列數字；每個重要數字都要說明它代表的盤勢含義。
2. 現貨技術面以 `01_latest_signal.json`、`02_recent_market_30d.csv` 為主。
3. 長期規則與勝率以 `04_long_term_backtest_summary.csv`、`05_operational_rule_backtest.csv`、`06_decision_tree_rules.csv` 為主。
4. 大盤情境資料以 `09_market_context_daily.csv`、`10_market_context_summary.csv` 為輔，用來補充三大法人、融資融券與市場情緒。
5. 期貨與選擇權以 `11_derivatives_recent_30d.csv`、`12_options_oi_profile_latest.csv`、`13_derivatives_signal_summary.json` 為主。
6. 衍生性商品資料只做「訊號品質與風險確認」，不要取代現貨布林帶規則。
7. 若期貨/選擇權資料不足，請明確寫「本次衍生性商品資料不足，判斷以現貨技術面為主」。

## 建議文章結構

1. 今日大盤表現
2. 技術面與布林帶位置
3. 期貨籌碼與價差
4. 選擇權壓力/支撐與情緒
5. 綜合格局判斷
6. 操作結論

## 目前程式判定

- 現貨狀態：IN｜從DN回到通道內第10天
- 現貨動作：等回測
- 下一步：等待：UP新突破且StartBreakoutPct>0.36%→追
- 衍生性商品偏向：cautious
- 衍生性商品風險：medium_high
- 寫作提醒：衍生性商品結構偏謹慎，文章可寫短線仍需觀察是否站回關鍵價位。

## 口吻

語氣可以像財經新聞，但要比一般新聞多一層判斷。避免使用「可能、或許」堆砌；可以說明條件，例如：

- 若站回某價位，代表跌勢暫時收斂。
- 若無法收復某價位，代表反彈仍屬弱勢。
- 若期貨空單維持高水位但未增加，代表空方沒有擴大攻擊，但避險壓力仍在。
```
