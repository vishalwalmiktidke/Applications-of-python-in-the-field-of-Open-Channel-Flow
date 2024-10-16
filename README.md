# Applications-of-python-in-the-field-of-Open-Channel-Flow
ASSIGNMENT NO. 01

Q.01) # To find the downstream depth of open channel
# Given data
Q = float(input("Enter the value of Discharge (m³/s): "))
T = int(input("Enter the value of top width (m): "))
g = float(input("Enter the value of acceleration due to Gravity (m/s²): "))
y1 = float(input("Enter the value of upstream depth (m): "))
Z = float(input("Enter the value of hump (m): "))

# Discharge per meter width
q = Q / T
print("The value of discharge per meter width is:", q)

# Area Calculation
A1 = T * y1
print("The value of upstream area is:", A1)

# Calculation of Froude Number
Fr1 = ((Q**2 * T) / (g * A1**2))**0.5	
print("The value of Froude number is:", Fr1)

if Fr1 > 1:
    print("The flow is super Critical Flow")
else:
    print("The flow is Sub Critical Flow")

# Upstream Energy
E1 = y1 + (Q**2 / (2 * g * A1**2))
print("The value of Energy at initial section is:", E1)

# Downstream Energy
E2 = E1 - Z
print("The value of downstream Energy E2 is:", E2)

# Critical Depth
yc = (q**2 / g)**(1/3)
print("The value of critical depth is:", yc)

# Critical Energy
Ec = y1 + (Q**2 / (2 * g * A1**2)) + (yc - y1)  # Adjusted for clarity
print("The value of critical Energy is:", Ec)

if Ec > E2:
    print("Choking Condition")
else:
    print("SAFE")

# Calculation of Zmax
Zmax = E1 - Ec
print("The value of maximum hump is:", Zmax)

OUTPUT:
Enter the value of Discharge (m³/s): 4.8
Enter the value of top width (m): 2
Enter the value of acceleration due to Gravity (m/s²): 9.81
Enter the value of upstream depth (m): 1.6
Enter the value of hump (m): 0.1
The value of discharge per meter width is: 2.4
The value of upstream area is: 3.2
The value of Froude number is: 0.6772854614785963
The flow is Sub Critical Flow
The value of Energy at initial section is: 1.714678899082569
The value of downstream Energy E2 is: 1.614678899082569
The value of critical depth is: 0.837370824744677
The value of critical Energy is: 0.9520497238272458
SAFE
The value of maximum hump is: 0.7626291752553231
