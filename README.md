# Mr or Mrs?

One of the most difficult tasks in class, especially online classes, is the correct use of Mr. and Mrs. prefixes. For example, you see Mahdi Afarideh's name in the list and you don't know whether you should say Mr. Afarideh or Mrs. Afarideh. In this project, we plan to design a website that will help teachers in this important matter. 

In this site, there are two general situations, one when the user knows the gender of the name and wants to save it on the site and two when the user does not know and wants to find out through our site.

In the website a background covers the whole page, and in the middle of it is a transparent rectangle. We are careful so that the transparency is not so high that the text inside the rectangle cannot be read. The middle rectangle contains all your displayable content. This rectangle is only the size of it's contents, but to display it more beautifully, we use padding. The content consists of two parts that are placed horizontally next to each other. The first part is a form that consists of two entries. The first entry is in text form and it can be done if one already knows the answer. The second input is in the form of two radio buttons that allow the user to enter the desired name, enter it and this answer is saved for the future. The design spec of this website can be seen below:

![image](https://github.com/MahdiTheGreat/MahdiTheGreat.github.io/assets/47212121/d9608df4-430c-4842-a159-559435748f00)

and the implemenation is shown below:

![Screenshot 2023-08-09 at 11-00-19 Mr  or Ms](https://github.com/MahdiTheGreat/Mr-or-Mrs/assets/47212121/351fc0e2-9d69-42df-a51a-485bafe3a1ce)

After filling out the form, the user clicks on submit button and his request will be sent. For example below we fill the form with the name Xena:

![Screenshot 2023-08-09 at 10-59-57 Mr  or Ms](https://github.com/MahdiTheGreat/Mr-or-Mrs/assets/47212121/8568e37c-e01c-4fb9-bfe9-fb6650e309f1)

We consider the following in the implementation of the input form:

• The inputed name should have a maximum of 255 characters. 
• The name entered by the user must consist only of spaces, upper and lowercase English letters.
• The submit button should not perform the default behavior of the browser.

We use the following website to predict the gender of the given name:
https://api.genderize.io/?name=Xena
in the above link, the inputed name is Xena and the request is done as a GET and the inputed name is used as a query string. The output of this request is as follows:

{
"name":"Xena",
"gender":"Female",
"probability":0.96,
"count":49197
}

And therefore needs to be converted to an object in javascript. Error is also handled and shown on the website. 
The error could be because of the inability of the api to guess the gender or connection issues. The output on the website can be seen below:

![Screenshot 2023-08-09 at 10-58-41 Mr  or Ms](https://github.com/MahdiTheGreat/Mr-or-Mrs/assets/47212121/0dcd4aa0-4a9f-41c2-b6e2-4a505e5a0c40)

# Saved answers

There are times when the website makes a wrong prediction, in which case you can get the correct answer by asking the student. In this case, this website has the ability to store the correct answer.  
Finally, if the entered name is available, the the stored answer is displayed to the user.
If a gender has been already stored for a name and the user gives another answer, the
previous value will be deleted . If the user wants to delete the saved value for a name, 
after sending a request for that name, he can use the delete button that is displayed in the saved answers section. 
Notice that the saved answers section will only be displayed if there is a saved answer.

#step by step

We want to review the procedure of working with this website step by step. In this section:

scenario one:
1. The user wants to find the gender of the name "Hasan".
2. The user enters the name "Hasan" in the specified field and prediction is done.
3. The prediction result will be displayed to him and he can save it if necessary

scenario two:
1. The user wants to find the gender of the name "Hasan", but predicts that this name is male.
2. The user enters the name "Hasan" in the specified field and prediction is done.
3. The prediction result is displayed to the user, but the user prefers to use his knowledge and male gender Save for this name.
   
scenario three:
1. The user wants to find the gender of the name "Hasan", but he already entered this name and saved the result.
2. The user enters the name "Hasan" in the specified field and prediction is done.
3. The prediction result is displayed to the user, next to it it is stated that the result is already saved for this name.
4. The user can change the saved result or delete it.

scenario four:
1. The user wants to find the gender of the name "Hasan", but previously entered this name and saved the desired result.
2. The user enters the name "Hasan" in the specified field and prediction is done.
3. The prediction result is displayed to the user, next to it it is stated that the result is already saved for this name.
4. The user can change the saved result or delete it.

This website is published by github and is viewable via the link below:
https://mahdithegreat.github.io/









