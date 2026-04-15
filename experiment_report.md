# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600148
**Name:** Nguyen Duc Dung
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario                          | Agent Response                                                          | Accuracy (1-10) | Notes                                                        |
| --------------------------------- | ----------------------------------------------------------------------- | --------------- | ------------------------------------------------------------ |
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.            | 10              | Chính xác, chọn sản phẩm electronics với giá cao nhất hợp lý |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1               | Sai, chọn outlier với giá bất thường                         |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai khi sử dụng garbage data vì dữ liệu chứa nhiều lỗi: duplicate IDs, wrong data types (price là string "ten dollars" thay vì số), outliers, category rỗng, và price bằng 0.
->Khi agent tìm sản phẩm electronics với giá cao nhất, nó chọn Nuclear Reactor vì 999999 lớn hơn Laptop 1200, dẫn đến kết quả không hợp lý. Điều này chứng minh rằng data quality kém có thể làm hỏng hiệu suất của AI, quan trọng hơn cả việc tối ưu prompt.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý hoàn toàn. Thí nghiệm cho thấy ngay cả với logic agent đơn giản và prompt rõ ràng, dữ liệu rác vẫn dẫn đến kết quả sai lệch do outliers và lỗi. Data quality kém làm hỏng nền tảng của AI, trong khi prompt tốt chỉ có thể bù đắp một phần. Việc xây dựng pipeline ETL để validate và clean data là bước quan trọng để đảm bảo độ tin cậy của hệ thống AI.
