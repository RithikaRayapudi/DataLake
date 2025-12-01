
# **README.md**

## **Delta Lake Assignment – ShopEZ E-commerce Orders**

This project implements a full **Delta Lake data pipeline** on Databricks for an e-commerce company, **ShopEZ**.
The dataset contains order-level information generated daily from multiple countries.

The assignment demonstrates key Delta Lake capabilities:

---

## **Tasks Implemented**

### **1. Ingest sample order data**

Load sample JSON-like records into a Spark DataFrame.

### **2. Add derived column**

Convert `order_timestamp` to `order_date` for partitioning.

### **3. Write DataFrame as Delta**

Store as a Delta table partitioned by:

* `country`
* `order_date`

### **4. Verify storage structure**

Check partition folders created in the Delta table path.

### **5. Partition pruning**

Run filtered queries to show Delta scans only required partitions.

### **6. Time Travel**

Update Delta data, then query older versions using:

```
versionAsOf
```

### **7. Schema Evolution**

Append new data containing:

* `payment_method`
* `coupon_code`

Using:

```
.option("mergeSchema", "true")
```

### **8. Updates & Deletes**

Demonstrate ACID operations:

* Mark low-value orders as CANCELLED
* Delete orders below a threshold

### **9. Optimize**

Run:

```
OPTIMIZE
OPTIMIZE ... ZORDER BY (customer_id)
```

### **10. Small File Problem**

Generate many small partitions and then compact them using OPTIMIZE.

---

## **Technologies Used**

* Apache Spark
* Delta Lake
* Databricks
* Python (PySpark)

---

