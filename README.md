# HiFav

HiFav is a Social Chat Android app built to connect you to everyone you love.

## By [**Linus Brian Okoth**](https://www.linkedin.com/in/linus-okoth-273b12143/)

For any bugs or messages drop me an [email](brianlinus1753@gmail.com)

## Methodology
I will display any progress in a the chronological order in which they are implemented and I will also give a brief explanation on
whatever the features I am implementing are.

## Requirements:
- Download and Install ***AndroidStudio 3.5*** or later versions.
- Start an Empty project with _API level 28_ or later versions.
- Confirm support for latest ```androidx``` libraries

## Configuration
The app will be running on data as different users will be sending messages to other users. Thus I chose a database that can easily
facilitate this process as follows: 
-  I added Firebase Acess Control through the built ***assistant*** in Android studio. First you have to lig into android studio
then using the assistant bar add access and Authentification by Firebase.
- Click on add Google cloud storage to the app. 

### _Common Bugs_ 
***Firebase connection failed*** - This is caused either caused by poor internet connection which can be solved by accessing a stronger 
internet connection or, if the account signed into your Android Studio account is not a gmail account. In that case you need to update
to a gmail account. 

***Build Graddle Failed*** - This is mostly as a result of difference in your graddle app version and the just added Firebase version
which can also be solved by opening graddle app file and copying updating your dependency to the required version.

## Functionality and Major Features

## Custom TaskBar

### Implementation Specifics
-  Open your style and create a customized style of choice. Then create a new layout with the ```root element``` as the toolbar.
- In this progect we will be automatically choosing ***Relative Layout**
-  Set the properties in your new layout including adding the background color and setting the layout height to wrap content.
- It advisable thgat throughout this project you give every new element added an inituitive id that matches what it performs or
the functions of the library it implements.
- Include your layout in ```activity_main.xml``` since thats the main xml page being rendered when oncreate in the
```MainActivity.java``` is invoked when your app runs. It defines the landing page in other words. You will need to
use the ```<include></include>``` tag and call your layout between them.
- Include the toolbar in  ```MainActivity.java``` by creating a new instance of the ```ToolBar``` class then setting the values
and rendering the bar with your custom name eg  ```
        setSupportActionBar(mToolBar);
        getSupportActionBar().setTitle("HiFav");```

### _Common Bugs_
***Instance of ```ToolBar``` not recognized*** Delete the import line for the ```ToolBar``` and use the autophelp to import
a matching version.

## TabLayout to that switches between different fragments.
-  Define the ```appBarlayout``` in the ```activity_main.xml``` as a container and cut the previously defined ```<include></include>```
inside them
- Most importantly add the ***view_property*** just below and outside the ```appBarLayout```. 
- Then create three fragments that will be represented on the ```MainActivity.java```
- Currently we are presented with a special case of three fragments that need to be read and rendered in ```MainActivity.java```, a 
class with absolutely no relation to these fragments. This is where we apply our ***Adapter knowlege*** to enable us collect location
from ```MainActivity.java``` and decide which fragement to be rendered. Thus we create a new class that extends Fragment Page Adapter,
the adapter for fragments. 
- Finally we go to ```MainActivity.java``` and instatiate Tabs access Adapter, the newly created class and pass the view page object
to configure swiped through different Tabs.

### _Common Bugs_
***App Crashes when you try to switch through different fragments*** Delete your fragments and recreate them while unchecking the 
checkboxes that request to set default functionalities for your fragments.

***Graddle Crash*** or ***Project cant access*** ```depreciated support:appcompativity.design``` add this line to your graddle
to use the updated version of the library ```implementation 'com.google.android.material:material:1.1.0'```

### _Demonstration of above implementations_

<img src="HiFav.gif" width=200><br>
