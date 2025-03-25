# 🎬 SynthFlix: Movie Recommender with Synthcity

For more info refer to my blog - [Lights, Camera, Synthetic Data: Building Better Movie Recommendations with Synthcity](https://medium.com/@udedhia/lights-camera-synthetic-data-building-better-movie-recommendations-with-synthcity-16d5981c1b94)

Welcome to **SynthFlix**, a hands-on experiment that builds a movie recommendation system using synthetic data generated with [Synthcity](https://github.com/vanderschaarlab/synthcity). This project simulates realistic user behavior using privacy-safe synthetic data and evaluates model performance across different data scenarios.


## Project Overview

In real-world ML, access to real user data is often limited due to privacy policies like GDPR or CCPA. This project shows how to:

- Generate synthetic data from real user ratings.
- Benchmark and optimize synthetic data generators.
- Train and evaluate a matrix factorization model (MF_SVD).
- Compare performance across real, synthetic, and hybrid data setups.


## Key Experiments

Seven experiments were designed to test various combinations of real and synthetic data:

| No. | Experiment             | Train On             | Test On     | Purpose                      |
|-----|------------------------|----------------------|-------------|------------------------------|
| 1   | Real → Real            | 8K real              | 2K real     | Baseline performance         |
| 2   | TVAE → Real            | 2K synthetic         | 2K real     | Synthetic data utility       |
| 3   | Real + TVAE → Real     | 8K real + 2K synth   | 2K real     | Data augmentation            |
| 4   | TVAE → TVAE            | 2K synth             | 2K synth    | Internal fidelity            |
| 5   | Real → TVAE            | 8K real              | 2K synth    | Generalization               |
| 6   | Small Real → Real      | 2K real              | 2K real     | Control setup                |

> 💡 *Findings*: Augmented data (Real + Synthetic) gave the best RMSE, while synthetic-only models were usable but less accurate.


## Tools & Libraries Used

- `Synthcity` for synthetic data generation & benchmarking.
- `scikit-surprise` for matrix factorization (SVD).
- `matplotlib`, `seaborn` for visualizations.
- `Optuna` for hyperparameter optimization.


## How to Run

1. **Clone the repo:**

```bash
git clone https://github.com/urmidedhiacmu/SynthCity_MovieRecommenderSystem.git
cd SynthCity_MovieRecommenderSystem
```

2. **Install the dependencies:**

```bash
pip install -r requirements.txt
```
3. **Run the notebook:**
```bash
jupyter notebook
```
> Make sure you have the MovieLens 100K dataset available (either locally or from Kaggle).

## Author

Built by **Urmi Dedhia**  
🎓 Master's in Artificial Intelligence and Innovation @ CMU (MSAII)  
🔗 [LinkedIn](https://www.linkedin.com/in/urmidedhia/)
