# Mailgun

NSL Mailgun Extension for Yii2

## Version
Aktuelle Version: 1.0.5

## Installation

```
php composer.phar require --prefer-dist itbeauftragter/yii2-nsl-mailgun "*"
```

## Usage

Configure it in the application configuration:

```php
'components' => [
    ...
    'mailer' => [
        'class' => 'itbeauftragter\mailgun\Mailer',
        'key' => 'key-example',
        'domain' => 'mg.example.com',
        'endpoint' => 'api.eu.mailgun.net'
    ],
    ...
],
```

To send an email, you may use the following code:

```php
Yii::$app->mailer->compose('contact/html', ['contactForm' => $form])
    ->setFrom('from@domain.com')
    ->setTo($form->email)
    ->addTags(['Tag1', 'Tag2'])
    ->setSubject($form->subject)
    ->send();
```
