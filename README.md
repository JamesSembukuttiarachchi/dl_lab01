# Lab 1: Introduction to Python Libraries for Deep Learning

## Objective  
Gain knowledge and skills related to Python libraries and frameworks needed for deep learning.  

## Introduction  
This lab familiarizes you with common Python libraries used in deep learning:  

- **NumPy** – Supports large, multi-dimensional arrays and matrices with mathematical functions.  
- **Matplotlib** – Creates static, animated, and interactive visualizations in Python.  
- **Pandas** – Provides tools for data manipulation and analysis.  
- **Seaborn** – A high-level interface for statistical data visualization based on Matplotlib.  


## **Task 1**  

1. **Random Array Creation**  
   - Create a random `4x4` array from an exponential distribution (NumPy).  

2. **Histogram Visualization**  
   - Create a random `100000x1` array from the same exponential distribution.  
   - Visualize histogram along with uniform and normal distributions.  
   - Modify bins and plot view for better visualization.  
   ```python
   plt.hist(np.random.rand(100000), density=True, bins=100, histtype="step", color="blue", label="rand")
   plt.axis([-2.5, 2.5, 0, 1.1])
   plt.legend(loc="upper left")
   plt.title("Random distributions")
   plt.xlabel("Value")
   plt.ylabel("Density")
   plt.show()
   ```

3. **3D Plot**  
   - Plot `Z = X**2 + Y**2` using Matplotlib 3D.  
   - Limit `x` and `y` to `[-5, 5]`.  

4. **Correlation Analysis**  
   - Calculate **Pearson** and **Spearman** correlation for `[HP, Attack, Defense, Sp. Ark, Sp. Def, Speed]` features from `seaborn_tutorial.ipynb`.  
   - Visualize with a heatmap displaying values.  

---

## **Task 2** – *Au Nano Particle Dataset*  

1. **Data Filtering**  
   - Load `Au_nanoParticle_dataset.csv` into a DataFrame.  
   - Keep only: `N_total`, `N_bulk`, `N_surface`, `R_avg`.  

2. **Display Data**  
   - Show the first 20 samples.  

3. **Statistical Summary**  
   - Calculate **mean**, **standard deviation**, and **quartiles** for each feature.  

4. **Histograms**  
   - Plot histograms for each feature in a `1x4` layout.  

5. **Pairplot**  
   - Use Seaborn’s `pairplot()` for scatter plots and histograms.  

6. **Advanced PairGrid**  
   - Diagonal: histogram + KDE.  
   - Lower half: bivariate KDE plot.  
   - Upper half: bivariate histogram.  
   ```python
   g = sns.PairGrid(new_df)
   g.map_upper(sns.histplot)  # bivariate histogram
   g.map_diag(sns.histplot)   # histogram + KDE
   g.map_lower(sns.kdeplot)   # bivariate KDE
   ```

---
