## Parking Lot System 🚗🏍️🚚

A multi-floor **parking lot system** that supports multiple vehicle types (**Car, Bike, Truck**) with **thread-safe operations**, **efficient spot allocation**, and a built-in **test suite**.  

✅ **Single-file implementation:** The entire code is in `cr1.py`.  
✅ **Well-commented & documented:** Includes **docstrings & inline comments** for easy understanding.  

---

## **📌 Key Features**  
- **Vehicle Class Hierarchy** – `Car`, `Bike`, and `Truck` classes with type-specific spot allocation.  
- **Nearest Spot Allocation** – Uses **Min-Heap (`heapq`)** for **O(1) nearest spot retrieval** (cars/bikes) and sorted checks for trucks.  
- **Thread Safety** – **Per-floor locks** prevent race conditions in concurrent operations.  
- **Full Object-Oriented Design** – `ParkingLot`, `Floor`, and `Vehicle` encapsulate all functionalities.  
- **Built-in Test Suite** – **17+ test cases** covering normal operations, edge cases, and stress scenarios.  

---

## **🛠️ Installation**  

### **1️⃣ Requirements**  
- **Python 3.6+** required  
- No external dependencies (only uses Python's standard libraries: `heapq`, `threading`, `dataclasses`, `enum`)  

### **2️⃣ Clone the Repository**  
```bash
git clone https://github.com/shashvat1412/parking-lot-system.git
cd parking-lot-system
```

---

## **🚀 Usage**  

The **entire code is inside `cr1.py`**, including **comments and docstrings for better understanding**.  

### **Initialize a parking lot with 3 floors and 10 spots per floor**  
```python
parking_lot = ParkingLot(num_floors=3, spots_per_floor=10)
```

### **Park a car**  
```python
parking_lot.park_vehicle("KA-01-1234", "Car")
```

### **Park a truck (requires 2 consecutive spots)**  
```python
parking_lot.park_vehicle("MH-02-5678", "Truck")
```

### **Check available spots on floor 0**  
```python
print(parking_lot.get_available_spots_per_floor(0))
```

### **Remove a vehicle**  
```python
parking_lot.leave_vehicle("KA-01-1234")
```

### **Check if the parking lot is full**  
```python
print(parking_lot.is_full())
```

---

## **🔍 Design Highlights**  

### **🔹 Object-Oriented Design**
- **Encapsulation**: `ParkingLot`, `Floor`, and `Vehicle` classes handle responsibilities separately.  
- **Extensibility**: Easy to add new vehicle types like `ElectricCar`.  

### **🔹 Concurrency Handling**
- **Per-floor locks (`threading.Lock`)** allow parallel parking across different floors.  
- **Global lock for `vehicle_map`** ensures safe lookups and modifications.  

### **🔹 Efficiency**
- **Min-Heap (`heapq`)** ensures **fast nearest-spot allocation**.  
- **Set operations (`set()`)** provide **O(1) vehicle presence checks**.  

---

## **🧪 Testing**  

### **Run all test cases**  
```bash
python cr1.py
```
✅ **Test Cases Included:**  
- `test_park_truck()` → Ensures trucks get consecutive spots.  
- `test_truck_fragmented_spots()` → Trucks cannot park in non-consecutive spots.  
- `stress_test()` → Simulates **900+ vehicles** to validate system stability.  

---

## **🤝 Contribution**  

Contributions are welcome! Open an **issue** or **PR** for:  
- Adding **new vehicle types** (e.g., `ElectricCar`).  
- Implementing a **CLI/API interface**.  

---

### **Final Notes**  
- ✅ **Single-file implementation** – No extra modules required.  
- ✅ **Fully documented with comments and docstrings.**  
- ✅ **Easily understandable structure, suitable for quick evaluations.**  

---



