# Defect Detection on AI Images

A PyTorch-based project for training and testing a binary classifier on image data. Includes CLI support for training and inference.

---

## Setup Instructions

0. **Clone the repository**
   ```bash
   git clone https://github.com/arseny-k/it-jim_ak1_2025
   cd it-jim_ak1_2025
   ```

1. **Create a virtual environment (optional)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Verify folder structure**
   Ensure your training and test images are in:
   - `data/train/`
   - `data/test/`

   Image filenames should follow the format: `image_<id>_<label>.png`

---

## How to Use

### Train the Model
```bash
python main.py train
```

**Optional Arguments:**
```bash
--data-dir   Path to training data (default: ./data/train)
--epochs     Number of training epochs (default: from config)
--augment    Enable data augmentation (flip, rotate, jitter)
```

Example:
```bash
python main.py train --data-dir ./data/trainee_dataset/train --epochs 20 --augment
```

---

### Run Inference on Test Set
```bash
python main.py test
```

**Optional Arguments:**
```bash
--data-dir   Path to test data (default: ./data/test)
--output     Output CSV filename (default: test_predictions.csv)
```

Example:
```bash
python main.py test --data-dir ./data/trainee_dataset/test --output results.csv
```

---

## Evaluation Metrics
- Micro F1 score on test set: **0.9600**

---

## Notes
- The best model is saved to `models/best_model.pth`
