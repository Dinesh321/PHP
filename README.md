<?php

$host = "localhost";
$user = "root";
$pass = "";
$db = "bank";

mysql_connect($host,$user,$pass);
mysql_select_db($db);



if(isset($post['username'])) {
	$username = $_POST['username'];
	$password = $_POST['password'];



$sql = "SELECT * FORM users WHERE username='",$username,"' AND password='",$password,"' LIMIT 1";
$res = mysql_query($sql);
if (mysql_num_rows($res)==1){
	echo "YOU HAVE SUCCESSFULLY LOGGED IN";
	exit();

} else {

echo "Invalid Login Information. Please Return to the Previous Page.";
exit();


}

}

?>

<html>
<head>
</head>
<body>
<form method="post" action="login.php">
Username: <input type="text" name="Username"/><br/><br/>
Password: <input type="Password" name="Password"/><br/><br/>
<input type="submit" name="submit" value="Login"/>
</form>
</html>
