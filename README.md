# MSCS-634 Lab 5: Hierarchical Clustering and DBSCAN

**Shawn Miller**  
**Advanced Big Data and Data Mining (MSCS-634-B01)**

## Purpose

I used the scikit-learn Wine dataset to compare hierarchical clustering and DBSCAN. I explored and standardized the data, tested different settings, and used PCA plots, a dendrogram, and clustering scores to review the results.

## Results

- **Hierarchical:** I tested 2–6 clusters. Three worked best, with a **0.277 silhouette**, **0.790 homogeneity**, and **0.783 completeness**. The dendrogram showed how the groups were connected.
- **DBSCAN:** I tested 24 combinations of `eps` and `min_samples`. At `eps=2.4` and `min_samples=5`, it found **2 clusters** and **36 noise points**. Its non-noise silhouette was **0.327**, with **0.504 homogeneity** and **0.552 completeness** when noise was treated as its own label.

Hierarchical clustering matched the main wine groups better and included every sample. DBSCAN helped identify noise, but it was sensitive to the settings. Its silhouette excludes noise points, so the two silhouette scores are not directly comparable.

## Challenges and choices

I standardized the 13 features because they have different scales. A smaller `eps` created more noise, while a larger value merged groups. I used PCA only for graphs; the models used all 13 features. The known wine types were used only to check results.

## Files and running the lab

- `MSCS_634_Lab_5.ipynb` — notebook with code, results, graphs, and explanations
- `README.md` — this summary
- `requirements.txt` — required packages

Install the packages with `python -m pip install -r requirements.txt`, then open the notebook in Jupyter and select **Run All**. The Wine dataset loads directly from scikit-learn.