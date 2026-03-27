<!DOCTYPE html>
<html>
<head>
<title>Form Validation</title>
<style>
    .container { width: 400px; margin: 50px auto; background: white; padding: 25px; box-shadow: 0px 0px 10px gray; }
    input, button { width: 100%; padding: 8px; margin: 8px 0; }
</style>
<script>
function validateForm() {
    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let phone = document.getElementById("phone").value;
    let emailPattern = /^[^\s]+@[^\s]+\.[a-z]{2,3}$/;
    
    if(name == "") { alert("Name cannot be empty"); return false; }
    if(!email.match(emailPattern)) { alert("Enter valid Email"); return false; }
    if(phone.length !== 10) { alert("Enter valid 10-digit phone number"); return false; }
    
    alert("Form Submitted Successfully");
    return true;
}
</script>
</head>
<body>
    <div class="container">
        <h2>Registration Form</h2>
        <form onsubmit="return validateForm()">
            <label>Name</label><input type="text" id="name">
            <label>Email</label><input type="text" id="email">
            <label>Phone Number</label><input type="text" id="phone">
            <button type="submit">Submit</button>
        </form>
    </div>
</body>
</html>

