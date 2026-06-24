# Credit Card Transaction Risk Analysis Dashboard

Đồ án môn Thực hành Kỹ thuật Phân tích Dữ liệu (THKTPTDL)

## Mô tả

Phân tích rủi ro giao dịch thẻ tín dụng từ dataset không có nhãn gian lận thật. Hướng tiếp cận: xây dựng hệ thống `RiskScore` dựa trên các đặc trưng hành vi giao dịch để nhận diện giao dịch cần theo dõi.

## Cấu trúc

| File | Mô tả |
|------|-------|
| `creditcard_risk_analysis.ipynb` | Notebook chính — FINAL CODE V2 |
| `cc_info.csv` | Thông tin thẻ tín dụng (hạn mức, địa chỉ) |
| `transactions.csv` | Dữ liệu giao dịch gốc |
| `creditcard_merged_basic.csv` | Dữ liệu đã merge & feature engineering |
| `creditcard_risk_dashboard_v2.html` | Dashboard tương tác (xuất từ notebook) |
| `Do_an_THKTPTDL_creditcard.pptx` | Slide thuyết trình |

## Mạch xử lý

```
Dữ liệu gốc
→ Kiểm tra & Merge dữ liệu
→ Feature Engineering
→ EDA trước RiskScore
→ Phân tích tỷ lệ giao dịch so với hạn mức
→ Xây dựng RiskScore (điều chỉnh theo phân phối dữ liệu)
→ EDA sau RiskScore
→ ANOVA / Chi-square
→ Linear Regression / Logistic Regression / Decision Tree
→ So sánh mô hình
```

## Nhãn proxy

- `NeedReview = 1` nếu `RiskScore >= 2` — giao dịch cần theo dõi
- `PotentialFraud = 1` nếu `RiskScore >= 3` — giao dịch nghi ngờ cao

## Tech stack

Python 3 · pandas · numpy · matplotlib · scipy · statsmodels · scikit-learn
