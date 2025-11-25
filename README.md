# AIML-Task-8
# 🏙️ My City Lifestyle Clustering Analysis

## 📌 Project Goal: Figuring Out City Groups
I tackled this project to figure out how to group cities automatically using data—basically, letting the machine decide what a 'lifestyle segment' looks like. I used **K-Means Clustering** because it's the perfect tool for unsupervised learning when you just need to find those natural groupings.

***

## 📊 The Data I Used
I worked with the `city_lifestyle_dataset.csv`. It's packed with key metrics that define a city's character. I focused on these core features:
- **population_density**
- **avg_income**
- **internet_penetration**
- **avg_rent** 🏠
- **air_quality_index** 🌬️
- **public_transport_score** 🚌
- **happiness_score** 😊
- **green_space_ratio** 🌳

***

## ⚙️ My Process: How I Built the Model
1.  **Prep Work:** I had to standardize the data first. If I hadn't, a feature like `avg_income` would totally dominate `happiness_score` just because the numbers are bigger. I used `StandardScaler` to put everything on an even playing field.
2.  **Finding 'K':** I wasn't sure how many groups to look for, so I ran the **Elbow Method**. The resulting plot showed a clear elbow, which helped me confirm that **three clusters** were the optimal number to aim for.
3.  **The Fit:** Then I ran the K-Means algorithm to assign every city to one of those three segments.
4.  **Checking the Work:** I calculated the **Silhouette Score** ($\approx 0.356$) to confirm that the groups were actually separated well enough.

***

## ✨ My Findings & Visuals
I ended up with three key visuals that really tell the story of the data. You can find them saved in the repository:

1.  **Elbow Method for Optimal K (`elbow_curve.png`):**
    * This plot was my guide for choosing K. The drop in inertia slows down significantly right after $K=3$, making it the logical choice for my model.

2.  **Cluster Separation via PCA (`pca_clusters.png`):**
    * Since I had 8 features, I used **PCA** to shrink the data down to a 2D plot. The result visually proves that my three color-coded groups are distinct and separated in the data space.

3.  **Cluster Profiling Heatmap (`cluster_heatmap.png`):**
    * This is the most helpful part. It shows the average traits of each cluster, which lets me give them a real-world label.
        * **Cluster 1 (High-End Hubs):** I saw high averages for `avg_income`, `happiness_score`, and `public_transport_score`.
        * **Cluster 2 (Densely Populated):** This group had low scores for income/rent but high `population_density`.
        * **Cluster 0:** This segment was generally the middle-of-the-road group across the board.

***

## 💻 Dependencies
You'll need these standard Python libraries to run my code: `pandas`, `matplotlib`, `seaborn`, and `scikit-learn`.
