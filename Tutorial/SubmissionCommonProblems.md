# Common problems of custom visuals 
The custom visuals team has written and reviewed many custom visuals. Some of the common issues found with custom visuals are: 

1. __Input dataView is not validated when it is converted to internal data model__  
Do not expect that dataView will always have required properties and arrays are filled in. You should clear your visual’s content if you don’t have enough information provided to display it – for example when a mandatory field bucket is not filled in. Also, do not assume that type of data from the dataset will be only the one you expected.  
This problem causes errors to be thrown from the update method of the visual and unexpected behavior when the visual is updated. 
2. __Labels and elements of the visual are overlapped__
Use a different type of datasets to fully test your visual with various sets of elements of your visual. Resize your visual to check how elements of the visual are responding to that. Increase/decrease text sizes if property pane provides those settings. 
This problem causes overlapping of elements of the visual. Such issues are critical when you cannot interact with an element that is overlapped. 
3. __Numeric settings of the property pane are not validated in the code of the visual__
Test values provided by the property pane. This problem causes performance issues, console errors, or even crashing of the visual. 
4. __The visual throws errors in the console of the browser__
Any issue of the visual causing such errors should be fixed. 
5. __Data labels are not formatted__
Use different types of data to check if the data labels are formatted well
6. __Duplicated icon image definitions in CSS file are caused by the current version of Dev Tools__
7. __Version of the visual is not increased after update__
8. __The GUID of the visual is changed even if the visual is already published__
The GUID of the visual can be found in package.json, css and js files of the package
9. __Power Desktop BI usage the old code when an updated package is loaded__
For the Power BI Desktop to use the new updated code if/while debugging/verifying using a package file, the `"guid":` parameter in the `package.json` file needs to be updated. If the same GUID is used, the new code will not be executed. When releasing the code to the main master branch, the guid can/shall be the same. Please note that the recomended way to debugg the code is to use the Developer Visual in the Power BI Service and use the `pbiviz start` command to build
