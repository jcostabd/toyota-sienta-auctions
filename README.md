import pandas as pd

# Read auction text file
with open("sienta.txt", "r", encoding="utf-8") as f:
    lines = f.readlines()

data = []
for line in lines:
    # Example: adjust delimiter based on your file format
    parts = line.strip().split("|")  
    
    # Only keep valid rows (adjust columns as per your data)
    if len(parts) >= 5:
        data.append(parts)

# Define column names based on your dataset
df = pd.DataFrame(data, columns=["Lot No", "Grade", "Mileage", "Price", "Status"])

# Export to Excel
df.to_excel("sienta.xlsx", index=False)

print("✅ Auction data exported to sienta.xlsx")
