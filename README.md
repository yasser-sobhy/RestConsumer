# RestConsumer
RestConsumer makes it very easy to write RESTful api consumers and to communicate with RESTful api servcies, see [QtSendGrid](https://github.com/yasser-sobhy/QtSendGrid/blob/master/src/sendgridclient.h) to see how to use it to consume write a web service.

## Example
You just need to inherit RestConsumer to get a GET, PUT, POST, DELETE operations for your client

  #ifndef SENDGRIDCLIENT_H
  #define SENDGRIDCLIENT_H

  #include "sendgrid/restconsumer.h"
  #include "sendgrid/sendgridmessage.h"

  #include <QString>

  namespace SendGrid {

  class SendGridClient : public Gurra::RestConsumer
  {

  public:
      SendGridClient();
      SendGridClient(QByteArray apiKey, QByteArray host = "https://api.sendgrid.com/v3", QHash<QByteArray, QByteArray>  requestHeaders = {}, QString urlPath = {});

      void sendEmail(SendGridMessage &msg);

  private:
      QByteArray version = "1.0";
      QString urlPath;
      QString mediaType;
  };

  }
  #endif // SENDGRIDCLIENT_H

RestConsumer is a part of [Gurra](https://github.com/yasser-sobhy/Gurra) ui framework.
