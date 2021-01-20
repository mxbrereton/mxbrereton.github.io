<html>
<head>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
<title>Component 2 Field Generator</title>
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

</head>
<body>
<h1>Create Your Data</h1>

<form name="gen" action="" method="GET"><br>
<label for="field_name">Select the field:</label>
<select id="field_name" name="field_name">
	<option value="1">Branch</option>
	<option value="2">Sales Rep</option>
	<option value="3">Payment Method</option>
	<option value="4">option 4</option>
</select>
<button type="button" onclick="draw_table()">Generate Data</button>
</form>

<table id="myTable">

</table>

<script>
var field_name = document.getElementById("field_name");

function gen_data(f){
if(f=="1"){var opts = ["Doncaster", "Meadowhall", "Sheffield", "Manchester"];}
else if(f=="2"){var opts = ["Amelia Gower", "John Fort", "Helen Barr", "Mohamed Dinah", "Sarah Brough", "Michael Price"];}
else if(f=="3"){var opts = ["VISA", "MasterCard", "Pay Monthly", "Cash", "Cheque"];}
else if(f=="4"){var opts = ["choice14", "choice24", "choice34", "choice44"];}
else{
var opts = ["error picking options"];}

var l = [];
var i;
for(i=0;i<500;i++){
var r = opts[Math.floor(Math.random()*4)];
//var r = "testing";
l.push(r);
}
return l;
}

function draw_table(){
var f = document.getElementById("field_name").value;
var table = document.getElementById("myTable");

var c = gen_data(f);
var i;

for(i=0;i<500;i++){
var row = table.insertRow();
var cell = row.insertCell();
cell.innerHTML = "<td>"+c[i]+"</td>";
}

document.body.appendChild(table);

}

function main(){
//need to get the choice from the table
//generate the data
//create the table


}

</script>

</body>
</html>
