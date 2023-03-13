#HTML CODE

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   
    <script src= "filename.js" > </script>
    <input type="button" value="create Table" onclick="CreateTable()" />
<hr />
<div id="dvTable"></div>

</head>
<body>
</body>
</html>


#JAVASCRIPT CODE


function CreateTable() {
    
    var mydata = new Array();
    mydata.push(["NAME ", "AGE", "DOB","EMAIL","COMPANY"]);
    mydata.push(["Abhinav bhardwaj", "22","05/7/2001","abhi123@gmail.com","Geminisolutions"]);
    mydata.push(["Abhinav bhardwaj", "22","05/7/2001","abhi123@gmail.com","Geminisolutions"]);
    mydata.push(["Abhinav bhardwaj", "22","05/7/2001","abhi123@gmail.com","Geminisolutions"]);
    mydata.push(["Abhinav bhardwaj", "22","05/7/2001","abhi123@gmail.com","Geminisolutions"]);

    
    var table = document.createElement("TABLE");
    table.border = "1";

    
    var columnCount = mydata[0].length;

    //Add the header row.
    var row = table.insertRow(-1);
    for (var i = 0; i < columnCount; i++) {
        var headerCell = document.createElement("TH");
        headerCell.innerHTML = mydata[0][i];
        row.appendChild(headerCell);
    }

    //Add the data rows.
    for (var i = 1; i < mydata.length; i++) {
        row = table.insertRow(-1);
        for (var j = 0; j < columnCount; j++) {
            var cell = row.insertCell(-1);
            cell.innerHTML = mydata[i][j];
        }
    }

    var dvTable = document.getElementById("dvTable");
    dvTable.innerHTML = "";
    dvTable.appendChild(table);
};
