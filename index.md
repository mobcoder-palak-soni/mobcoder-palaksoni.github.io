<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>AJAX-API</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
    integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous">
    </script>

<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
    integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous">
    </script>
  
  </head>
  <body>
    <h1 style="text-align: center">
    API
    </h1>
    <table id="table1" class="table table-success"></table>
    <button type="button" onclick="myFunction()" >Get</button>
    <button type="button" onclick="myfunc()" >Post</button>
    <button type="button" onclick="myfun1()" >PUT</button>


    <script>
        function myFunction(){
      $.ajax({
          url: "http://dummy.restapiexample.com/api/v1/employees",
          type : "GET",
            success : function(data){

                var A = "<tr><th>id</th><th>Employee Name</th><th>Employee Salary</th><th>Employee Age</th></tr>";
                for( x=0;x<data.data.length;x++){
                  
                  
    A += '<tr>';
    A += '<td>'+ data.data[x].id + '</td><td>' + data.data[x].employee_name + '</td><td>' + data.data[x].employee_salary + '</td><td>' + data.data[x].employee_age + '</td>';
    A += '</tr>';
                        
                }
                $("#table1").append(A);
          }
      });
        }



    function myfunc(){
    let post = "PALAK SONI";
   
const url = "http://dummy.restapiexample.com/api/v1/create";
let x = new XMLHttpRequest();
x.open('POST',url , true);
x.send(post);
x.onload = function () {
    if(x.status >=200&&x.status<300) {
        console.log("Post successfully created!") ;
    }
}
//x.send(post);
 
}

function myfun1(){
    let PUT = "palak soni";
   const url = "http://dummy.restapiexample.com/api/v1/update/21";
   let x = new XMLHttpRequest();
   x.open('PUT',url , true);
   x.send(PUT);
   x.onload = function () {
       if(x.status >=200&&x.status<300) {
           console.log("PUT successfully UPDATE!") ;
       }
   }
//    x.send(post);
    
}
    </script>

</body>
</html>
