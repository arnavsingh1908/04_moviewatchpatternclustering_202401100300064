# 04_moviewatchpatternclustering_202401100300064


---

### **Project Title:**  
**User Segmentation and Behavioral Clustering from Movie Watch Data**

---

### **Project Description**

In today’s data-rich streaming landscape, understanding user behavior is crucial for delivering personalized content and optimizing viewer engagement. This project focuses on clustering users based on their movie-watching habits using a dataset titled `movie_watch.csv`, which contains information on individual watch time, genre preferences, and ratings given.

The goal is to identify distinct viewer segments—or *archetypes*—that can help streaming platforms tailor content recommendations, target marketing campaigns, and improve overall user satisfaction.

---

### **Steps Undertaken**

#### 1. **Data Cleaning and Preprocessing**
- All records with `watch_time_hour = 0` were dropped to focus on actively engaged users.
- The dataset was checked for null values and inconsistencies.
- Categorical features like `genre_preference` were encoded using one-hot encoding.
- Numeric features (`watch_time_hour`, `avg_rating_given`) were scaled using `StandardScaler` to ensure equal weighting.

#### 2. **Feature Engineering**
- One-hot encoded genre preferences to represent categorical genres in binary form.
- Ratings were optionally categorized into “Low” and “High” based on median splits for analysis purposes.
- Combined all engineered features into a single matrix for modeling.

#### 3. **Clustering with K-Means**
- K-Means clustering was chosen due to its simplicity, speed, and effectiveness with Euclidean distances.
- The optimal number of clusters (`K=3`) was determined using methods like the elbow method and silhouette scores.
- K-Means was trained on the scaled data, and each user was assigned a cluster label.

#### 4. **Cluster Validation**
- Evaluated the quality of clustering using **Silhouette Score**, which indicated reasonably well-separated clusters.
- Generated **confusion matrices** (visualized as heatmaps) to compare actual genre preferences and rating behaviors with cluster assignments—showing strong alignment between clusters and user behaviors.

#### 5. **Cluster Interpretation**
The clusters were profiled and interpreted as:
- **Cluster 0:** High watch time, high ratings, and action/thriller genres — *Engaged Enthusiasts*
- **Cluster 1:** Medium watch time, mixed genres and ratings — *Balanced Viewers*
- **Cluster 2:** Low watch time, low ratings, preference for drama/romance — *Casual Critics*

---

### **Tools & Technologies Used**
- **Python**
- **Pandas** (data handling)
- **NumPy** (numeric operations)
- **Matplotlib & Seaborn** (visualizations)
- **Scikit-learn** (scaling, encoding, clustering, evaluation)

---

### **Outcome**
This project successfully clustered users into meaningful behavioral groups. These clusters can help streaming platforms:
- Offer personalized recommendations based on user segments.
- Target content or marketing toward specific viewer types.
- Improve retention by identifying low-engagement users early.

The approach is modular and scalable, and it provides a strong foundation for integrating machine learning into real-world recommendation systems.

---




![Screenshot 2025-04-22 121544](https://github.com/user-attachments/assets/7eebccf1-22ab-4497-9e3d-c6e81a0afa78)
![image](https://github.com/user-attachments/assets/9b648b1f-0374-4cf6-ae2c-96e0ca2dd083)
![Screenshot 2025-04-22 120517](https://github.com/user-attachments/assets/10240fc9-439d-4b66-80be-ed2ee5499eb2)
![Screenshot 2025-04-22 120457](https://github.com/user-attachments/assets/4eee3e10-a321-4071-afea-cb67fba3ef29)
![Screenshot 2025-04-22 120356](https://github.com/user-attachments/assets/a1b5694a-1677-47b4-8734-486081181026)
![Screenshot 2025-04-22 120322](https://github.com/user-attachments/assets/bd37c07d-e93f-4079-b918-2ca85a3bca50)


### **Result of the Project**

The main result of this project is the successful **segmentation of users into three distinct behavioral clusters** using K‑Means clustering on their movie-watching data. Here's a breakdown of the key results:

---

### 🔹 **1. Clustering Outcome**
Using features like `watch_time_hour`, `avg_rating_given`, and encoded `genre_preference`, users were grouped into the following clusters:

| **Cluster** | **Watch Time** | **Rating Style** | **Genre Preference**     | **User Type**           |
|-------------|----------------|------------------|---------------------------|--------------------------|
| **0**       | High           | High             | Action, Thriller          | **Engaged Enthusiasts** |
| **1**       | Medium         | Medium           | Comedy, Drama (Mixed)     | **Balanced Viewers**    |
| **2**       | Low            | Low              | Romance, Drama            | **Casual Critics**      |

These clusters reflect **clear, actionable behavior patterns** among users.

---

### 🔹 **2. Evaluation Metrics**
- **Silhouette Score**: ~**0.51**  
  - Indicates **moderate cluster separation**, which is quite good for human behavioral data.
- **Heatmaps**:  
  - Showed strong alignment between **clusters and user preferences**, confirming that users within the same cluster share similar genres and rating behaviors.

---

### 🔹 **3. Insights Generated**
- **Cluster 0** users are binge-watchers with a strong preference for high-action content. They are ideal for early access promotions and premium releases.
- **Cluster 2** users watch less and are more critical. This group may need re-engagement strategies or lighter content.
- **Cluster 1** represents average viewers with mixed tastes—best served with diverse or trending recommendations.

---

### ✅ **Final Result Summary**
The clustering process turned raw behavioral data into **three well-defined user segments**, offering:
- Improved understanding of viewer behavior
- A foundation for **personalized recommendation systems**
- Insights for **targeted content marketing**

These results demonstrate that even a basic unsupervised learning model like K-Means can deliver **tangible business value** when applied thoughtfully to user data.
