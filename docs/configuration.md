---
title: Configuration Options
---

The following can be configured in the file `local.config.php` located in the config directory.

## Thumbnails

- `thumbnails`
	- Set the maximum dimensions for derivative images for media files.
	- Options for large, medium, and square. Defaults for these are 800, 200, and 200 respectively (all sizes are pixels)

- `thumbnailer_options`
	- Default is `Omeka\File\Thumbnailer\ImageMagick`. 
	- Also available are `Omeka\File\Thumbnailer\Imagick` and `Omeka\File\Thumbnailer\Gd`

## PHP Path

- `phpcli_path`
	- Set the path the the php version you want to use.
	- Default is to attempt to detect correct path to PHP. Use this option to specify a path if needed in your server configuration. For example: 
```
    'cli' => array(
        'phpcli_path' => '/usr/bin/php55',
    ),
```


## Mail

- `mail` 
- Default is to use Sendmail (this is set up in `application/config/module.config.php`)
- If using SMTP use this example configuration, added to the end of `local.config.php` (see the [zend-mail docs](https://docs.zendframework.com/zend-mail/transport/smtp-options/) for clarification):
```
    'mail' => [
        'transport' => [
            'type' => 'smtp',
            'options' => [
                'name' => 'localhost',
                'host' => '127.0.0.1',
                'port' => 25, // 465 for 'ssl', and 587 for 'tls'
                'connection_class' => 'smtp', // 'plain', 'login', or 'crammd5'
                'connection_config' => [
                    'username' => null,
                    'password' => null,
                    'ssl' => null, // 'ssl' or 'tls'
                    'use_complete_quit' => true,
                ],
            ],
        ],
    ],
```
