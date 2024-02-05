# The second part

Write two scripts: consumer.py and producer.py. Using RabbitMQ, organize a simulated email campaign to your contacts
using queues.

Using the ODM Mongoengine, create a model for a contact. The model must include the following fields: full name, email,
and a boolean field that is set to False by default. It means that the message hasn't been sent to the prospect and will
become True when it is sent. Other fields for the information load are up to you.

When you run the producer.py script, it generates a certain number of fake contacts and writes them to the database.
Then it places a message in the RabbitMQ queue containing the ObjectID of the created contact, and so on for all
generated contacts.

The consumer.py script receives a message from the RabbitMQ queue, processes it, and simulates sending a message via
email with a stub function. After sending the message, you need to set the boolean field for the contact to True. The
script runs constantly waiting for messages from RabbitMQ.

## Additional task

Enter an additional field for the phone number in the model. Also, add a field for the preferred method of sending
notifications - SMS by phone or email. Let producer.py send contacts to different queues for SMS and email. Create two
scripts, consumer_sms.py and consumer_email.py, each of which receives its own contacts and processes them.