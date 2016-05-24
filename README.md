# Yii2 reCAPTCHA widget

[Yii2](http://www.yiiframework.com) [reCAPTCHA](https://www.google.com/recaptcha/intro/index.html) widget.

## Installation

### Composer

The preferred way to install this extension is through [Composer](http://getcomposer.org/).

Either run

```php composer.phar require gbksoft/yii2-recaptcha-widget "*"```

or add

```"gbksoft/yii2-recaptcha-widget": "*"```

to the require section of your composer.json

## Usage

[Register](https://www.google.com/recaptcha/admin) a new site.

Add captcha attribute to model:

```php
public $captcha;

public function rules()
{
    return [
        [
            'captcha',
            \gbksoft\recaptcha\validators\RecaptchaValidator::class,
            'secret' => '<your-secret>'
        ]
    ];
}
```

Add field to view:

```php
<?= $form->field($model, 'captcha')->widget(\gbksoft\recaptcha\widgets\Recaptcha::class, [
    'clientOptions' => [
        'data-sitekey' => '<your-sitekey>'
    ]
]) ?>
```

## Info
See [reCAPTCHA documentation](https://developers.google.com/recaptcha)
