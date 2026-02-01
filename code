function sendMail() {
  var first = 0;
  var last = 2
  var email = 3;
  //var ccmail = "";
  //let id = '1LlmMgcATJK9pW_oKntPHLNZzGdBvt'

  //var image = DriveApp.getFileById(id).getAs("image/png");
  //var logo = {"logo": image}

  //const fromEmail = 'business@yourdomaindotcom'
  const fromName = 'YourBusinessName'

  



  
  var file = DriveApp.getFileById("1QWpHFLnRbMP6LrdJm444kQIQ89-DIP9C");


  var emailTemp = HtmlService.createTemplateFromFile("email");

  var ws = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Sheet1");

  var data = ws.getRange("A2:D" + ws.getLastRow()).getValues();

  data.forEach(function(row){
    
    emailTemp.fn = row[first];
    emailTemp.address = row[last];
    var htmlMessage = emailTemp.evaluate().getContent();
    GmailApp.sendEmail(
      row[email], 
      "Marketing Test Emails", 
      "Your email dosen't support HTML", 
      { 
        //from: fromEmail,
        name: fromName, 
        htmlBody: htmlMessage,
        //cc: ccmail,
        //inlineImages: logo, 
        attachments: [file]
      }

    );
  

  });

}
