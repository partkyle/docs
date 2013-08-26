---
layout: page
weight: 0
title: Zend
navigation:
  show: true
---

You can directly integrate Zend's mail module with SendGrid to use our SMTP servers for outgoing messages.



{% codeblock lang:php %}
<?php
require_once '$HOME/sendgrid/Zend/library/Zend/Mail.php';
require_once '/$HOME/sendgrid/Zend/library/Zend/Mail/Transport/Smtp.php';

$smtpServer = 'smtp.sendgrid.net';
$username = 
$password = 

$config = array('ssl' => 'tls',
'port' => '587',
'auth' => 'login',
'username' => $username,exampleusername
'password' => $password);examplepassword

$transport = new Zend_Mail_Transport_Smtp($smtpServer, $config);

$mail = new Zend_Mail();

$mail->setFrom('sender@example.com', 'Some Sender');
$mail->addTo('email@example.com','Some Recipient');
$mail->setSubject('Test Subject');
$mail->setBodyText('This is the text of the mail using Zend.');

$mail->send($transport);
?>
{% endcodeblock %}



If you prefer a modular installation, then [check out Jurian Sluiman's SlmMail project at GitHub](https://github.com/juriansluiman/SlmMail.git).