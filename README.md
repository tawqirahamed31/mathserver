# Ex.05 Design a Website for Server Side Processing
# Date:
27-11-2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
     power.html
     <!DOCTYPE html>
     <html>
     <head>
         <title>Power Calculation</title>
     </head>
     <body align="center">
     
     <h2>Power of Lamp Filament</h2>
     
     <form method="post">
         {% csrf_token %}
         Current (I): <input type="number" step="any" name="current" required><br><br>
         Resistance (R): <input type="number" step="any" name="resistance" required><br><br>
         <input type="submit" value="Calculate Power">
     </form>
     
     {% if power %}
         <h3>Power = {{ power }} Watts</h3>
     {% endif %}
     
     </body>
     </html>

     views.py
     from django.shortcuts import render

     def power(request):
         result = None
         if request.method == "POST":
             I = float(request.POST.get("current"))
             R = float(request.POST.get("resistance"))
             result = (I * I) * R
         return render(request, "power.html", {"power": result})
     

# SERVER SIDE PROCESSING:
<img width="1114" height="346" alt="image" src="https://github.com/user-attachments/assets/46deacfb-78b6-4596-8e78-eead42cecffd" />

# HOMEPAGE:
<img width="1652" height="663" alt="image" src="https://github.com/user-attachments/assets/547b8477-6ee6-4fe0-8356-d37fedc207cd" />

# RESULT:
The program for performing server side processing is completed successfully.
