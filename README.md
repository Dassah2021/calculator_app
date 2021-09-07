# calculator_app
#html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
    
</head>
<body>
    
    <div class="card">
        <div class="calc-head">
            <input maxlength="10" disabled="disabled" type="text" id="result"  style="color: black;">
        </div>
        <div class="cal-body">
            <div>
                <input type="button" class="btn" value="C" onclick="cNumber()">
                <input type="button" class="btn" value="+/-">
                <input type="button" class="btn" value="%" onclick="insertNumber('%')">
                <input type="button" class="btn" value="/" onclick="insertNumber('/')">
            </div>
            <div>
                <input type="button" class="btn" value="7" onclick="insertNumber(7)">
                <input type="button" class="btn" value="8" onclick="insertNumber(8)">
                <input type="button" class="btn" value="9" onclick="insertNumber(9)">
                <input type="button" class="btn " value="X"onclick="insertNumber('*')">
            </div>
            <div>
                <input type="button" class="btn" value="4" onclick="insertNumber(4)">
                <input type="button" class="btn" value="5" onclick="insertNumber(5)">
                <input type="button" class="btn" value="6" onclick="insertNumber(6)">
                <input type="button" class="btn " value="-"onclick="insertNumber('-')">
            </div>
            <div>
                <input type="button" class="btn" value="1" onclick="insertNumber(1)">
                <input type="button" class="btn" value="2" onclick="insertNumber(2)">
                <input type="button" class="btn" value="3" onclick="insertNumber(3)">
                <input type="button" class="btn " value="+"onclick="insertNumber('+')">
            </div>
            <div>
                <input type="button" class="btn" value="0" onclick="insertNumber(0)">
                <input type="button" class="btn" value="." onclick="insertNumber('.')">
                <input type="button" class="btn" value="DEL" onclick="deleteNumber()">
                <input type="button" class="btn " value="="onclick="calculate()">
            </div>
        </div>
    </div>
    <p style="display: flex; justify-content: center; margin-top: 20px;">©All Right Reserved By Group II</p>

   <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
     <script src="./script.js"></script>

</body>
</html>

#css
*{
    margin: 0;
    padding: 0;
}
body {
  background: linear-gradient(
    90deg,
    #3b3c5c,
    #5d486e,
    #82537a,
    #a65e7f,
    #c86d7e,
    #e38078,
    #f69870,
    #ffb56b
  );
}
 .card {
    margin: 0 auto;
    max-width: 350px;
    text-align: center;
    margin-top: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
    font-size: 0;
}
.card:hover{
    box-shadow: 0 16px 32px 0 rgba(0, 0, 0, 0.2);
}
.calc-head #result {
    width: 335px;
    height: 100px;
    font-size: 32px;
    font-weight: bold;
    text-align: right;
    padding: 0 5px;
    letter-spacing: 2px;
}
.calc-head #result:focus {
    border: 1px solid #8f8f9d;
    outline: none;
}
.btn {
    width: 87px;
    height: 70px;
    font-size: 16px;
    background-color: #1f2326;
    color: white;
}
.cal-body div input:last-child{
    background-color: slateblue;
}
.btn:hover{
    background-color:pink;
}

@media (max-width:350px){
    .btn {
        width: 73px;
    }
    .calc-head #result {
        height: 80px;
    }
}


#javascript
var resultField = $('#result');
function insertNumber (number) {
    var existingNumber = resultField.val()
    resultField.val(existingNumber + number )
};
function cNumber() {
    resultField.val('')
}
function calculate(){
    var result = eval(resultField.val())
    resultField.val(result)
}
function deleteNumber (){
    var valou = resultField.val()

    if(valou!='') {
        resultField.val(resultField.val().slice(0,-1));
    }
}
