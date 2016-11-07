odoo 9, Automatically send email when I submited a form?? 
---------------------------------------------------------------

via Automated Action, server Action, mail template , Is it possible??

.. code:: python

	import smtplib
	
	sender = 'username'
	receivers = 'destinations'
	message = """hai         """
	
	smtpObj = smtplib.SMTP(host='smtp.gmail.com', port=587) 
	smtpObj.ehlo()
	smtpObj.starttls()
	smtpObj.ehlo()
	smtpObj.login(user="username", password="password") 
	smtpObj.sendmail(sender, receivers, message
	print "Successfully sent email

https://www.odoo.com/forum/help-1/question/odoo-9-automatically-send-email-when-i-submited-a-form-110471

