
#  Parking Lot System 🚗🏍️🚚

A **multi-floor parking lot system** with thread-safe operations, efficient spot allocation, and a built-in test suite. The system supports **Cars, Bikes, and Trucks**, ensuring optimal space utilization and quick vehicle lookups.  

✅ **Single-file implementation (`cr1.py`)** containing the entire code.  
✅ **Min-Heap (`heapq`) for nearest spot allocation.**  
✅ **Thread-safe operations using `threading.Lock` for concurrency.**  
✅ **17+ test cases covering edge scenarios and stress tests.**  

---

## 📌 Features  
- **Object-Oriented Design** – `ParkingLot`, `Floor`, and `Vehicle` classes for modularity.  
- **Optimized Spot Allocation** – Min-Heap for O(1) retrieval and sorted spot checks for Trucks.  
- **Concurrency Handling** – Thread synchronization for safe parallel operations.  
- **Comprehensive Test Suite** – Edge cases, fragmented parking, and stress scenarios included.  

---

## 🛠 Installation  

### **Requirements**  
- **Python 3.6+**  
- Standard libraries used: `heapq`, `threading`, `dataclasses`, `enum`  

### **Clone the Repository**  
```bash
git clone https://github.com/shashvat1412/parking-lot-system.git
cd parking-lot-system
```

---

## 🚀 Usage  

### **Initialize a parking lot with 3 floors and 10 spots per floor**  
```python
parking_lot = ParkingLot(num_floors=3, spots_per_floor=10)
```

### **Park a vehicle**  
```python
parking_lot.park_vehicle("KA-01-1234", "Car")
parking_lot.park_vehicle("MH-02-5678", "Truck")
```

### **Check available spots on a floor**  
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

## 🔍 Design Overview  

### **OOP Principles**  
- **Encapsulation** – `ParkingLot`, `Floor`, and `Vehicle` classes handle responsibilities separately.  
- **Extensibility** – Can add new vehicle types like `ElectricCar`.  

### **Concurrency Handling**  
- **Per-floor locks (`threading.Lock`)** allow parallel parking.  
- **Global lock for `vehicle_map`** ensures thread-safe lookups.  

### **Efficiency**  
- **Min-Heap (`heapq`)** ensures **fast nearest-spot allocation**.  
- **Set operations (`set()`)** provide **O(1) vehicle presence checks**.  

---

## 🧪 Testing  

### **Run all test cases**  
```bash
python cr1.py
```
✅ **Test Cases Included:**  
- `test_park_truck()` → Ensures trucks get consecutive spots.  
- `test_truck_fragmented_spots()` → Trucks cannot park in non-consecutive spots.  
- `stress_test()` → Simulates **900+ vehicles** to validate system stability.  

---

## 🤝 Contribution  

Open an **issue** or **PR** for:  
- Adding **new vehicle types** (e.g., `ElectricCar`).  
- Implementing a **CLI/API interface**.  

---




