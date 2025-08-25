1️⃣ Import libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Optional: improve plot style
plt.style.use("seaborn-v0_8")

2️⃣ Example data (replace with your official datasets)
data = {
    "year": [2018, 2019, 2020, 2021, 2022]*2,
    "type": ["Onshore"]*5 + ["Offshore"]*5,
    "capacity_factor": [28, 30, 29, 31, 32, 40, 42, 41, 43, 44],
    "cost_per_mwh": [60, 58, 57, 56, 55, 90, 88, 87, 85, 84]
}

df = pd.DataFrame(data)

# 3️⃣ Boxplot: Capacity Factor Comparison
plt.figure(figsize=(8,5))
sns.boxplot(data=df, x="type", y="capacity_factor", palette="Set2")
plt.title("Capacity Factor Comparison: Onshore vs Offshore")
plt.ylabel("Capacity Factor (%)")
plt.show()

4️⃣ Line chart: Cost Evolution Over the Years
plt.figure(figsize=(10,6))
sns.lineplot(data=df, x="year", y="cost_per_mwh", hue="type", marker="o")
plt.title("Cost Evolution of Wind Energy in the Netherlands")
plt.ylabel("Cost per MWh (€)")
plt.show()

5️⃣ Statistical Summary Table
summary = df.groupby("type")[["capacity_factor", "cost_per_mwh"]].describe()
display(summary)

6️⃣ Export summary to CSV (optional)
summary.to_csv("wind_energy_summary.csv")

