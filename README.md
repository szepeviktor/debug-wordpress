# Debug WordPress

[![theories](https://img.shields.io/badge/more-theories-purple)](https://github.com/stars/szepeviktor/lists/theory)

Tools and techniques for debugging WordPress.

## Incoming HTTP requests

Dump POST request body to the error log.
Copy [this snippet][debug-post-requests] to wp-config.
Follow error log: `tail -f error_log`

## HTTP response headers

Open developer tools in your browser.

### Tools

- https://redbot.org/
- https://securityheaders.com/
- https://www.webpagetest.org/

## HTTP response body

View page source in your browser.

### Tools

- https://validator.w3.org/
- https://www.webpagetest.org/

## PHP code

Dump hooks (actions and filters) fired to a file.
Copy [this snippet][debug-hooks] to `wp-includes/plugin.php`.
Follow the log: `tail -f wp-content/debug-hooks.log`

## PHP errors

Follow PHP error log: `tail -f error_log`

## Outgoing HTTP requests

Log requests.

### Tools

- `snitch` plugin
- `log-http-requests` plugin

## Cron events

Cron can be web-based and CLI-based.

Log events.

## Database queries

Log queries before they are executed, see `EXPLAIN` statement.

## Emails

Log sent emails.

## Support my work

Please consider supporting my work as these lists take years to compile.

[![Sponsor](https://github.com/szepeviktor/.github/raw/master/.github/assets/github-like-sponsor-button.svg)](https://github.com/sponsors/szepeviktor)

Thank you!

[debug-post-requests]: https://github.com/szepeviktor/wordpress-website-lifecycle/blob/master/debug/debug-post-requests.php
[debug-hooks]: https://github.com/szepeviktor/wordpress-website-lifecycle/blob/master/debug/debug-hooks.php
