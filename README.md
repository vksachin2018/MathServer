# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
DEVELOPED BY: SHRIKRISHNA V
REG. NO.: 212223040198



<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cylinder Surface Area Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: rgb(0, 0, 0);
    }
    #calculator {
        text-align: center;
        background-color: rgb(255, 0, 0);
        padding: 30px;
        border-radius: 10px;
    }
    form {
        margin-bottom: 2px;
    }
    .input-container {
        margin-bottom: 10px;
    }
    label {
        display: flex;
        margin-bottom: 10px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        margin-top: 10px;
    }
    input[type="number"] {
        width: 200px;
        padding: 8px;
        border-color: #000000;
        box-sizing: border-box;
        border-radius: 100px;
    }
    button {
        background-color: #000000;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    }
    button:hover {
        background-color: #ffffff;
        color: #000000;
    }
    #result {
        font-size: 18px;
        font-weight: bold;
        color: aliceblue;

    }
    .rd{
        color: #ffffff;
    }
    .topic{
        color: #ffffff;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    }
    h3{
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    }
</style>
</head>
<body>

<div id="calculator">
    <h2 class="topic
    ">Cylinder Surface Area Calculator</h2>
    <h3>SHRIKRISHNA V (212223040198)</h3>
    <form id="cylinderForm">
        <div class="input-container">
            <label for="radius" class="rd">Radius:</label>
            <input type="number" id="radius" required>
        </div>
        <div class="input-container">
            <label for="height" class="rd">Height:</label>
            <input type="number" id="height" required>
        </div>
        <button type="submit">Calculate</button>
    </form>

    <div id="result">Surface Area: <span id="surfaceArea"></span></div>
</div>

<script>
document.getElementById("cylinderForm").addEventListener("submit", function(event) {
    event.preventDefault();
    var radius = parseFloat(document.getElementById("radius").value);
    var height = parseFloat(document.getElementById("height").value);
    var surfaceArea = 2 * Math.PI * radius * (radius + height);
    document.getElementById("surfaceArea").innerText = surfaceArea.toFixed(2);
});
</script>

</body>
</html>

```
```
Views.py

from django.shortcuts import render
def surfacearea(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        print('request.POST:', request.POST)
        r = request.POST.get('radius', '0') 
        h = request.POST.get('height', '0') 
        print('radius =', r)
        print('height =', h)
        area = 2 * 3.14 * int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'mathapp/math.html',context)
```
```
urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfacearea/',views.surfacearea,name="surfacearea"),
    path('',views.surfacearea,name="surfcaearea")
]
```

## SERVER SIDE PROCESSING:
![image](https://github.com/Wkrish28/MathServer/assets/144295230/df8a8077-cfc4-47e4-b0d9-cf848dc7cb6c)


## HOMEPAGE:
![image](https://github.com/vksachin2018/MathServer/assets/149366019/6eb944b6-660d-4a9e-bf66-ebcf735ab071)



## RESULT:
The program for performing server side processing is completed successfully.
