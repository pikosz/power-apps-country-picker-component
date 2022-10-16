# Power Apps country picker dialog component

#
#
### Overview
![](https://s4.gifyu.com/images/country-picker.gif)
#
#
## How to use
###### 1. Download MSAPP file from this repository
######  2. Import MSAPP file into your application as below
![](https://s4.gifyu.com/images/import-cmp.png)
######  3. Add component to your application as below & set it's height as Parent.Height and width as Parent.Width where Parent is the Screen.
![](https://s1.gifyu.com/images/country-picker-how-to-add.gif)
######  4. Define countries for users to pick in below format or leave default
###### (Default list is based on https://worldpopulationreview.com/country-rankings/country-codes)
![](https://s4.gifyu.com/images/country-picker-countries.png)
######  5. Add button to your screen that will open country picker dialog. In that button set variable to store dialog visibility (example below).
#
```
Button - > OnSelect()
UpdateContext({varCountryPickerVisible: true});

Component -> OnCancel()
UpdateContext({varCountryPickerVisible: false});

Component -> OnSelect()
UpdateContext({varCountryPickerVisible: false});
```
######  After adding above code it should work as below

![](https://s4.gifyu.com/images/country-picker-button-gif.gif)
######  6. Now we just need to save selected country data in a variable (example below)
#
```
Component -> OnSelect()

UpdateContext(
    {
        varCountryPickerVisible: false,
        varCountrySelectedCode: Code,
        varCountrySelectedName: Name
    }
);

```
######  7. Now with the above variables you can display selected country in your application (example below).
###### (To display country flag based on ISO code I used trick described in this article of mine: https://medium.com/marek-pikosz/power-apps-display-any-countrys-flag-8b78c570b065)
![](https://s4.gifyu.com/images/country-picker-display-selected.gif)
#
#
### Common issues
###### 1. My screen controls are visible over country picker dialog
###### To prevent this issue always put Country Picker component at the top of the screen controls structure
#
#
### Need help?
If you need help wit the application or want to contribute please contact me via [LinkedIn](https://www.linkedin.com/in/marek-pikosz/).

### License
MIT
