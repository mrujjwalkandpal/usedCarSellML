# Used Car Price Predictor

Predicting the selling price of used cars in India from details like age, kilometres driven, fuel type and transmission. 

**Status:** In progress. EDA is complete; data cleaning and modelling are next.

## Dataset

- **Source:** <link to the Kaggle page you downloaded it from> (Car Dekho listings)
- **Size:** 4,340 rows, 8 columns
- **Columns:** `name`, `year`, `selling_price`, `km_driven`, `fuel`, `seller_type`, `transmission`, `owner`
- **Target:** `selling_price` (in ₹)

## Key findings from EDA

- Prices are heavily right-skewed: the median is ₹3.5 lakh but the most expensive car is ₹89 lakh, so a log transform will be needed.
- Automatic cars have a much higher median price (₹9.5 lakh) than manual cars (₹3.25 lakh).
- Dealers charge more than individuals; the median is ₹4.95 lakh for dealers against ₹3 lakh for individual sellers.
- Price falls with the number of previous owners: ₹4.5 lakh for first owners against ₹1.3 lakh for fourth owners and above.
- Kilometres driven has only a weak linear correlation with price (-0.19), so the relationship is probably non-linear.
- Data quality: no missing values, but 763 duplicate rows (about 17.6%) that need to be removed.


## Project structure

```
├── data/
│   ├── raw/             # original dataset (never edited)
│   └── processed/       # cleaned data (created by notebook 02)
├── notebooks/
│   ├── 01_eda.ipynb             ✅ done
│   ├── 02_data_cleaning.ipynb   ⏳ planned
│   └── 03_modelling.ipynb       ⏳ planned
├── models/              # saved trained model
├── requirements.txt
└── README.md
```

## How to run

```bash
git clone https://github.com/<your-username>/used-car-price-predictor.git
cd used-car-price-predictor
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Then open the notebooks in `notebooks/` in order.

## Roadmap

- [x] Exploratory data analysis
- [ ] Data cleaning (duplicates, brand extraction, outliers, log-transform target)
- [ ] Feature encoding and train/test split
- [ ] Model training and comparison (Linear Regression, Random Forest, Gradient Boosting)
- [ ] Evaluation (R², MAE, RMSE)
- [ ] Simple web app (Streamlit) for price prediction

## Tech stack

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Jupyter
