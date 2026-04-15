[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573954&assignment_repo_type=AssignmentRepo)

# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** adung2912d03@gmail.com
**Name:** Nguyen Duc Dung

---

## Mo ta

Bài lab này xây dựng một ETL pipeline tự động để xử lý dữ liệu. Pipeline bao gồm các bước: Extract, Validate (kiểm tra và loại bỏ dữ liệu không hợp lệ), Transform (chuẩn hóa category và tính giá giảm 10%), và Load (lưu ra CSV). Ngoài ra, đã thêm tính năng observability với logging số lượng records processed/dropped và timestamp. Thí nghiệm so sánh hiệu suất của agent AI khi sử dụng dữ liệu sạch vs dữ liệu rác để chứng minh tầm quan trọng của data quality.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas
```

### Chay ETL Pipeline

```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)

```bash
python agent_simulation.py
```

# Chạy script này để so sánh phản hồi của agent khi sử dụng dữ liệu sạch (processed_data.csv) và dữ liệu rác (garbage_data.csv).

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline đã xử lý thành công: 3 records hợp lệ được lưu vào processed_data.csv, 2 records bị loại bỏ (1 do price <= 0, 1 do missing category). Agent simulation cho thấy với dữ liệu sạch, agent trả lời chính xác (Laptop $1200), nhưng với dữ liệu rác, agent chọn sản phẩm không hợp lý (Nuclear Reactor $999999) do outliers và lỗi dữ liệu.
