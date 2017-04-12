<?php
$name=$_FILES['file']['name'];
$tmp_name=$_FILES['file']['tmp_name'];
$size=$_FILES['file']['size'];
 $extension=strtolower(substr($name, strpos($name, '.')+1));
if (isset($name)) {
	if (!empty($name)) {
		if (($extension=='jpg')||($extension=='jpeg')&&($size<2000)) {
		$location='uploads/';
		if(move_uploaded_file($tmp_name, $location.$name))
		{
			echo "uploaded!!";
		}
		else{
			echo "Error!!";
		}
	}else
	{
		echo "file should be jpg or jpeg and size less than 2Mb";
	}}else{
		echo "Choose a file";
	}
}
?>
<!DOCTYPE html>
<html lang="en">
<head>
  <title>UPLOAD</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <link rel="stylesheet" type="text/css" href="upload.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
 
</head>
<body>
<hr style="border: 1px solid  #00264d" />​
<div class="navbar">
<div class="navbar navbar-default">
<ul class="nav navbar-nav">
<li><a href="#">Home</a></li>
<li><a href="#">Upload</a></li>
<li><a href="#">About Us</a></li>
<li><a href="#">Contact</a></li>
</ul>
</div>
</div>
<div class="container-fluid">
<form action="practice.php" method="post" enctype="multipart/form-data" >
	<br/>
	<input  type="file" name="file"><br/>
	<input type="submit" value ="submit"/>
</form>
</div>
</body>
</html>
