# Recaptcha
Recaptcha for Nette Framework 2.4+

# Usage

## NEON configuration
```neon
parameters:
    recaptcha:
        sitekey: ...
        secret: ...
```

## Example

Add extension method:
```php
/**
 * @param \Nette\Forms\Container
 * @param string
 * @param string
 * @param string
 * @return \App\UI\Forms\Controls\Recaptcha
 */
Container::extensionMethod('addRecaptcha', function (Container $form, $name = 'recaptcha', $caption = 'Recaptcha', $message = 'Recaptcha validation failed.') {
    return $form[$name] = new App\UI\Forms\Controls\Recaptcha($caption, $message);
});
```

Add input in form
```php
$form = new Form($this, $name); // form must be attached to presenter
$form->addRecaptcha();
```

Latte template
```latte
{input recaptcha}
```

HTML
```HTML
...
<script src="https://www.google.com/recaptcha/api.js"></script>
</body>
</html>
```