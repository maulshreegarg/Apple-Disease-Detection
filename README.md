# Apple-Disease-Detection
A machine learning approach to disease setection in apples using digital image processing , SVM, GCLM and K means algorithm
Fruit_disease.fig contains the user interface designed in MATLAB uaing MATLAB GUIDE .
The main program is in Fruit_disease.m . The machine learning and statistics toolbox is necessary for this project . 
## methodogy
![image](https://github.com/maulshreegarg/Apple-Disease-Detection/assets/98210535/aa4c2585-5a80-42cc-8562-ea1dc1520a4e)
1. Design the GUI of the given project in GUIDE. The tool can be directly downloaded and utilized through MATLAB.
2. pushbutton1 is the browse image button.In this functions callback we get the user to select the image from the dataset and the image is resized according to the axis.The image selected is shown using handles.ImgData1
3. pushbutton3 is used for increasing the contrast of the given image using input image.
   This MATLAB code defines a callback function pushbutton2_Callback that is executed when a push button (presumably named pushbutton2) is clicked in a GUI (Graphical User Interface) application. Here's what each part of the code does:
function pushbutton2_Callback(hObject, eventdata, handles)
This line defines the callback function pushbutton2_Callback, which takes three input arguments: hObject, eventdata, and handles. These arguments are automatically passed to the function by MATLAB when the push button is clicked.
hObject is the handle of the object that triggered the callback, which in this case is the push button.
eventdata is reserved for future use and currently not used in the function.
handles is a structure that contains handles to all the GUI components. This structure is used to access and modify GUI components from within the callback function.

I3 = handles.ImgData1;
This line retrieves the image data stored in the ImgData1 field of the handles structure. It assumes that ImgData1 contains the original image data.

I4 = imadjust(I3, stretchlim(I3));
This line applies contrast adjustment to the original image I3 using the imadjust function. The stretchlim function is used to compute the contrast limits for the adjustment.

I5 = imresize(I4, [300, 400]);
This line resizes the adjusted image I4 to a size of 300x400 pixels using the imresize function. The resized image is stored in I5.

axes(handles.axes2);
This line sets the current axes of the GUI to axes2, which presumably is a handle to an axes object where the enhanced image will be displayed.

imshow(I5);
This line displays the resized and enhanced image I5 in the specified axes.

title('\color{white}Enhanced Image');
This line sets the title of the displayed image to "Enhanced Image" with white color.

handles.ImgData2 = I4;
This line updates the ImgData2 field of the handles structure with the enhanced image data I4.

guidata(hObject, handles);
This line updates the GUI's handles structure with the modified ImgData2 field, ensuring that the changes are preserved and accessible in other callback functions or parts of the GUI.
Overall, this callback function loads an image, enhances its contrast, resizes it, displays the enhanced image in a specified axes, and updates the GUI handles structure with the enhanced image data.
