# simple-content-locker-PHP
A very simple way to lock your content using PHP, wanted to make it as a WP Plugin but got busy during process and just used plugin to insert it instead. The way it works it pretty self explanatory actually. It just reads the url and if that ends with "?valuekey" than 



'''php
<?php
$uri = $_SERVER['REQUEST_URI'];  
$protocol = ((!empty($_SERVER['HTTPS']) && $_SERVER['HTTPS'] != 'off') || $_SERVER['SERVER_PORT'] == 443) ? "https://" : "http://";
$url = $protocol . $_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI'];
$parse = parse_url($url);
$path =$parse['query'];
if($path  == "valuekey"){ //change valuekey to whatever you want
  // Do nothing..page loads normally.
    }else{
echo "<script> location.href='/'; </script>";
        exit;
         // Redirects back to homepage
    }
?>
'''


some minor modifications will be required if you wanna use link tracking tags.
