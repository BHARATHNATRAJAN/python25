## 1. Student Attendance Analysis
A college maintains the daily attendance details of its students in the form of a list containing student IDs. Some students may have attended multiple sessions on the same day. The administration wants to identify the longest continuous sequence of sessions in which no student ID is repeated. Develop a solution that determines the maximum length of such a sequence.

```
stu = [101, 102, 103, 101, 104, 105]
long = 0
for i in range(len(stu)):
    seen = []
    for j in range(i, len(stu)):
        if stu[j] in seen:
            break
        seen.append(stu[j])
        if len(seen) > long:
            long = len(seen)
print(long)
```
## output:
<img width="816" height="883" alt="image" src="https://github.com/user-attachments/assets/dc9f6565-32d0-47ac-b260-ca0f1323abce" />

## 2. Online Shopping Price Analysis
An online shopping application stores the prices of products viewed by a customer during a browsing session. The customer wants to identify a continuous range of products that provides the maximum possible total discount value. Given the discount values, determine the maximum value that can be obtained from any continuous range.

```

dis = [2, -1, 3, 4, -2]
max = dis[0]
for i in range(len(dis)):
    total = 0
    for j in range(i, len(dis)):
        total = total + dis[j]
        if total > max:
            max= total
print(max)
```

## Output :
<img width="1292" height="823" alt="image" src="https://github.com/user-attachments/assets/e3a2d8d1-b1af-47a8-b4bc-c4d16884a602" />

## 3. Rainwater Collection System
A city installs buildings of different heights along a straight road. During rainfall, water gets collected between taller buildings. The engineering team needs to calculate the total amount of water that can remain trapped after heavy rainfall based on the heights of the buildings.

```
heights = [3, 0, 2, 0, 4]
water = 0
for i in range(len(heights)):
    left = max(heights[:i + 1])
    right= max(heights[i:])
    trapped = min(left, right) - heights[i]
    water = water + trapped
print(water)
```
## Output:

<img width="1347" height="880" alt="image" src="https://github.com/user-attachments/assets/eee27f5b-ae53-49c6-8388-9f931e10bf64" />

## 4. Employee Performance Analysis
A company stores the monthly performance scores of an employee for several months. The scores may contain both positive and negative values depending on the employee's performance. Management wants to identify the continuous period during which the employee achieved the highest overall performance.

```
scores = [2, -1, 3, 4, -2]
max= scores[0]
for i in range(len(scores)):
    total = 0
    for j in range(i, len(scores)):
        total = total + scores[j]
        if total > max:
            max = total
print("Maximum performance:", max)
```

## Output:
<img width="1527" height="803" alt="image" src="https://github.com/user-attachments/assets/ea910d7a-f6b1-4ad2-8a7e-d54f1513fdce" />


## 5. Product Sales Analysis
A retail company stores the daily sales quantity of a product for several consecutive days. Due to seasonal changes, some days may have negative adjustments. The company wants to identify the period that produced the highest multiplication of sales-related values. Develop a solution to determine this maximum product.

```
sales = [-2, 3, -4]
max = sales[0]
for i in range(len(sales)):
    product = 1
    for j in range(i, len(sales)):
        product = product * sales[j]
        if product > max:
            max = product
print("Maximum product:", max)
```
## output:
<img width="1202" height="722" alt="image" src="https://github.com/user-attachments/assets/f93a6c6c-58ee-47bd-bfa4-e76f9fffe374" />




## 6. Customer Purchase History
An e-commerce application stores the product IDs purchased by a customer in chronological order. The same product may appear multiple times. The system needs to determine the longest sequence of consecutive purchases in which every product ID is unique.

```
products = [101, 102, 103, 101, 104, 105]
long = 0
for i in range(len(products)):
    unique = []
    for j in range(i, len(products)):
        if products[j] in unique:
            break
        unique.append(products[j])
        if len(unique) > long:
            long = len(unique)
print("Longest sequence:", long)
```
## output:
<img width="1407" height="750" alt="image" src="https://github.com/user-attachments/assets/c131d585-e4e2-45e4-823f-0545baf81748" />


## 7. Bank Transaction Analysis
A bank stores transaction amounts for a customer's account. A continuous group of transactions may add up to a specific target amount. The auditing system needs to determine how many different continuous transaction groups produce exactly the specified amount.

```
trans = [1, 2, 3, 2, 1]
target = 5
count = 0
for i in range(len(trans)):
    total = 0
    for j in range(i, len(trans)):
        total = total + trans[j]
        if total == target:
            count = count + 1
print("Number of groups:", count)

```
## output:
<img width="1342" height="727" alt="image" src="https://github.com/user-attachments/assets/81cea625-2721-4412-9b58-570fa6832cd7" />


## 8. Employee Skill Grouping
A company receives a list of employee skill codes represented as strings. Employees having the same set of characters in their skill codes belong to the same skill category, even if the characters appear in a different order. The HR system needs to organize employees into appropriate skill groups.

```
skills = ["eat", "tea", "tan", "ate", "nat", "bat"]
groups = {}
for word in skills:
    key = ''.join(sorted(word))
    if key not in groups:
        groups[key] = []
    groups[key].append(word)

print(list(groups.values()))
```

## Output:
<img width="1507" height="821" alt="image" src="https://github.com/user-attachments/assets/97de2185-32c6-41d5-8c69-22346952d8c1" />


## 9. Network Packet Analysis
A network monitoring system receives packet identifiers in chronological order. The system must determine the longest sequence of consecutive packets whose identifiers form a continuous numerical sequence, regardless of their original order in the incoming data.

```
packets = [100, 4, 200, 1, 3, 2]
packets.sort()
longest = 1
current = 1
for i in range(1, len(packets)):
    if packets[i] == packets[i - 1] + 1:
        current = current + 1
    elif packets[i] != packets[i - 1]:
        current = 1
    if current > longest:
        longest = current

print("Longest sequence:", longest)
```
## output
<img width="1646" height="845" alt="image" src="https://github.com/user-attachments/assets/14851d60-23ec-467e-939b-7da9d963a9dd" />




## 10. Hospital Appointment Scheduling
A hospital receives appointment requests represented by starting and ending times. Some appointments overlap with each other. The scheduling system needs to combine overlapping appointment periods so that the final schedule contains only non-overlapping time ranges.
```
appoint = [[1, 3], [2, 6], [8, 10], [9, 12]]
appoint.sort()
result = []
for appoint in appoint:
    if not result or appoint[0] > result[-1][1]:
        result.append(appoint)
    else:
        result[-1][1] = max(result[-1][1], appoint[1])

print(result)
```

## output:
<img width="1557" height="782" alt="image" src="https://github.com/user-attachments/assets/b1f0c3c5-0e21-4389-bcda-24851c0fe646" />



