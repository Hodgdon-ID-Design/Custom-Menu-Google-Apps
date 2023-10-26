# Create A Custom Menu in Google Apps

This JavaScript code was created by me and used to generate custom menus in our spreadsheets. These menus enabled users to execute commands without the need to write any code. This functionality was particularly valuable for our LMS administrators, as they needed to regularly review admin and user lists to monitor additions and removals.

---

# Directions

## Add Menu

* Open the Google Sheets, Docs, or Forms file where you want to create the custom menu.
* Open the script editor by navigating to "Extensions" -> "Apps Script" or by pressing **`Alt + /`** on Windows or **`Option + /`** on Mac.
* In the script editor, create a function that will be triggered when the custom menu item is selected. For example:


`function myFunction() {`

  `// Perform the desired actions when the custom menu item is selected`

  `// This is just a placeholder function, replace it with your own code`

  `SpreadsheetApp.getActiveSpreadsheet().toast('Custom menu item selected!', 'Status', 3);`

`}`


### Code Breakdown

**`SpreadsheetApp.getActiveSpreadsheet()`**: This part of the code retrieves the currently active spreadsheet in Google Sheets.

**`.toast('Custom menu item selected!', 'Status', 3)`**: This part of the code displays a toast message in the spreadsheet. The toast() method takes three arguments:

* **`'Custom menu item selected!'`**: This is the message that will be displayed in the toast.
* **`'Status'`**: This is the title or caption for the toast message.
* **`3`**: This is the duration of the toast message in seconds. In this case, it will be displayed for 3 seconds.

## Create Menu

* Next, create a function to add the custom menu to the Google Sheets, Docs, or Forms file. For example:

`function onOpen() {`

`var ui = SpreadsheetApp.getUi();` 

`// For Google Sheets, use DocumentApp.getUi() for Google Docs, and FormApp.getUi() for Google Forms`

 `ui.createMenu('Custom Menu')`

 `.addItem('Custom Menu Item', 'myFunction')`

`.addToUi();`

`}`

### Code Breakdown
**`function onOpen() {`**: This line defines a function named onOpen(). In Google Apps Script, the onOpen() function is a special function that is automatically triggered when a user opens the Google Sheets document. It's commonly used to customize the user interface by adding custom menus or dialogs.

**`var ui = SpreadsheetApp.getUi();`**: This line retrieves the user interface (UI) for the currently open Google Sheets document. It stores it in the variable ui. The SpreadsheetApp.getUi() method is used to access the UI for Google Sheets.

`**ui.createMenu('Custom Menu')**`: This line creates a custom menu with the name "Custom Menu." You can replace "Custom Menu" with any name you want for your custom menu.

**`.addItem('Custom Menu Item', 'myFunction')`**: This line adds an item to the custom menu. The addItem() method takes two arguments:

**`'Custom Menu Item'`**: This is the label or name of the menu item that will appear in the custom menu.
**`'myFunction'`**: This is the name of the function that will be executed when the menu item is selected. In this case, it refers to the myFunction() function.
**`.addToUi();`**: This line adds the custom menu and its associated item(s) to the Google Sheets document's user interface, making it visible and accessible to users.

### Steps

In the **`onOpen`** function, **`ui.createMenu`** is used to create the custom menu with the name "Custom Menu". The **`addItem`** method is used to add a specific menu item, which displays the text "Custom Menu Item" and triggers the **`myFunction`** when selected.

* Save the script and close the script editor.
* Refresh the Google Sheets, Docs, or Forms file. You should now see the "Custom Menu" option in the menu bar.
* Click on the "Custom Menu" option, and you will see the "Custom Menu Item". When selected, it will execute the **`myFunction`** function.

You can modify the names and functionality according to your requirements. This approach can be applied to create custom menus in Google Sheets, Docs, and Forms by replacing the appropriate **`getUi()`** method for the respective file type.

_Note: When running the script for the first time, you may need to authorize the script to access your Google account and grant necessary permissions._
