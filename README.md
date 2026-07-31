# Intelligent-Automation-RPA

In this project, I'll be using UiPath to automate the creation of an invoice in a Word document, exporting it as a PDF using Microsoft Office Applications. The information from the invoice is obtained by UiPath from an Excel Spreadsheet using the Web Applications scope. The PDF invoice is then sent out to the staff for verification through Email/Outlook using Email Management. 

User Setup process for Word and Excel:
    The user (staff of a company) has to first create a data sheet, an Excel spreadsheet for containing the company activities or items, the quantity and price of each item. Next, the user has to create an invoice template in Word to allow UI Path to duplicate it and create multiple future invoices.

UiPath processes:
    Firstly, UiPath will open up an Excel spreadsheet that the user created and extract the information from sheet 1 called “Companies to bill”, such as: 
•	Company name
•	Company billing address
•	Company activity or item
•	Quantity
•	Price of each item

    UiPath will use the Read Range Workbook activity to extract the information (Web Applications scope) above for each company, and make the respective companies’ invoices by automatically inserting them into the Word template. (Microsoft Office Applications scope)

    Next, UiPath will then collate all the information with the same company name and combine them into one invoice from the first sheet. It will calculate the subtotal of all the information and save it in another sheet called “Invoices & Subtotal” (in the same Excel spreadsheet) using the Assign and Write Range Workbook. UiPath will also include the subtotal in the Invoice and automatically generate an invoice number through auto-incrementation. UiPath will also get the current Date and insert it in the Invoice. The invoice number and current Date will also be saved in the “Invoices & Subtotal” sheet.

    Additionally, once the invoice information is processed for each company, the information from the “Companies to bill” sheet will be moved and appended to another sheet called “Billed Company info” to avoid future duplicate invoices being created. 

    Finally, once the invoice is fully created in the Word document, UiPath will use the App/We Recorder function to automatically convert the Word document into a PDF using the Save as Adobe PDF button. The invoice is then sent to the staff for verification through Email/Outlook for checking. (Email Management)



<img width="427" height="253" alt="image" src="https://github.com/user-attachments/assets/f2ea2fc5-ff1e-49e3-9b49-c2c39f45a27d" />

You have to pin the invoice template as the first item in your Word document to let the program work; otherwise, it will not work properly, as it will open up the first thing under Word's Template list.
