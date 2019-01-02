<p align="center">
    <a href="https://www.mangoweb.cz/en/" target="_blank">
        <img src="https://avatars0.githubusercontent.com/u/38423357?s=200&v=4"/>
    </a>
</p>
<h1 align="center">Sylius SMS Manager Plugin</h1>

## Features

xxx

* xxx

## Installation

1. Run `$ composer require mangoweb-sylius/sylius-sms-manager-plugin`.
2. Register `\MangoSylius\SmsManagerPlugin\MangoSyliusSmsManagerPlugin` in your Kernel.
3. Import `@MangoSyliusSmsManagerPlugin/Resources/config/resources.yml` in the config.yml.
4. Your Entity `Channel` has to implement `\MangoSylius\SmsManagerPlugin\Model\SmsManagerChannelInterface`. You can use Trait `MangoSylius\SmsManagerPlugin\Model\SmsManagerChannelTrait`.
5. Your Entity `ShippingMethodTranslation` has to implement `\MangoSylius\SmsManagerPlugin\Model\SmsManagerShippingMethodInterface`. You can use Trait `MangoSylius\SmsManagerPlugin\Model\SmsManagerShippingMethodTrait`.
6. Include template `@MangoSyliusSmsManagerPlugin/channelSmsSegmentForm.html.twig` in `@SyliusAdmin/Channel/_form.html.twig`.
6. Include template `@MangoSyliusSmsManagerPlugin/shippingMethodSmsForm.html.twig` in `@SyliusAdmin/ShippingMethod/_form.html.twig`.
For guide to use your own entity see [Sylius docs - Customizing Models](https://docs.sylius.com/en/1.3/customization/model.html)

### Usage

first setup sms manager in channel, than setup sms text in shipping method.

You can use variables in the SMS text.

```
{{ orderNumber }}
{{ trackingNumber }}
{{ address.fullName }}
{{ address.company }}
{{ address.street }}
{{ address.postCode }}
{{ address.city }}
{{ address.provinceCode }}
{{ address.provinceName }}
{{ address.countryCode }}
```

## Development

### Usage

- Create symlink from .env.dist to .env or create your own .env file
- Develop your plugin in `/src`
- See `bin/` for useful commands

### Testing

After your changes you must ensure that the tests are still passing.
* Easy Coding Standard
  ```bash
  bin/ecs.sh
  ```
* PHPStan
  ```bash
  bin/phpstan.sh
  ```
License
-------
This library is under the MIT license.

Credits
-------
Developed by [manGoweb](https://www.mangoweb.eu/).