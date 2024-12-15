# README

## Project Structure

```
.
├── final_data/              # Contains preprocessed data
│   ├── test_df.pkl         # Preprocessed test data
│   └── train_df.pkl        # Preprocessed train data
├── final_features/         # Feature csvs
│   ├── 512_RoBERTa_attention/
│   ├── gemini_attention/
│   ├── period_longformer_att/
│   ├── time_series/
│   └── word_attention_glove/
├── models/                 # Models Stored here (empty now)
└── *.ipynb                # Jupyter notebooks for different components
```

## Running the Code

### Prerequisites
- Python 3.x
- Required packages (Python, TensorFlow, PyTorch, xgboost, catboost, Transformers)

### Data Preparation
The preprocessed data is stored in `final_data` directory in pickle format (`.pkl`). If you need to preprocess raw data:

1. Open `preprocessing.ipynb`
2. Modify the following variables to point to your raw data:
   - `train_path`: Path to your training CSV file
   - `test_path`: Path to your test CSV file
3. Run the notebook to generate the preprocessed data files

### Model Training and Evaluation

All metaclassifier notebooks are self-contained and can be run directly from their respective locations. They expect the preprocessed data to be in the `final_features` directory.

Available metaclassifiers:
- MetaClassifier_CatBoost.ipynb
- MetaClassifier_LSTM.ipynb
- MetaClassifier_TabNet_PCA.ipynb
- MetaClassifier_TabNet.ipynb
- MetaClassifier_XGBoost.ipynb

### Feature Engineering

Additional feature engineering notebooks are provided:
- feature_engineering.ipynb
- 512_RoBERTA_attention.ipynb
- period_gemini_att.ipynb
- period_longformer_attention.ipynb
- word_glove_attention.ipynb
- gemini_embed_generator.ipynb

Each notebook is self contained and can be run independently as long as the preprocessed data is available in the expected location. For generating gemini embeddings an API key is required.