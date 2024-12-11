# Triangle-Type-Checker
Python Project of Triangle Type Checker
#pthon project=triangle type checker:
#guided by shweta devdas mam
import math

def triangle_angle_type(a, b, c):
    # Check if the sides form a valid triangle of sides a,b,c
    if a + b > c and a + c > b and b + c > a:
        # Sort the sides to identify the largest side
        sides = sorted([a, b, c])
        # Using the Pythagorean theorem to check the type of triangle
        a, b, c = sides[0], sides[1], sides[2] 
        # c is the largest side
        if round(a*2 + b*2, 5) == round(c*2, 5):
            # Right triangle
            return "Right Triangle: One angle is 90 degrees."
        elif a*2 + b*2 > c*2: 
            # for Acute triangle
            return "Acute Triangle: All angles are less than 90 degrees."
        else: 
            #  for Obtuse triangle
            return "Obtuse Triangle: One angle is greater than 90 degrees."
    else:
        return "Not a valid triangle: The sum of any two sides must be greater than the third side."

# Input of triangle sides from user
try:
    side1 = float(input("Enter the first side: "))
    side2 = float(input("Enter the second side: "))
    side3 = float(input("Enter the third side: "))

    # Determine and print the type of triangle based on angles
    result = triangle_angle_type(side1, side2, side3)
    print(result)
except ValueError:
    print("Please enter valid numeric values for the sides.")
