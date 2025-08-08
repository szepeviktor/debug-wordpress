# Debug WordPress

[![theories](https://img.shields.io/badge/more-theories-purple)](https://github.com/stars/szepeviktor/lists/theory)

Tools and techniques for debugging WordPress.

## Incoming HTTP requests

Dump POST request body to the error log.  
Copy [this snippet][debug-post-requests] to `wp-config.php`.  
Follow error log: `tail -f error_log`

### Tools

- For AJAX requests: https://github.com/szepeviktor/qm-ajax
- For REST requests: https://querymonitor.com/wordpress-debugging/rest-api-requests/

## HTTP response headers

Open developer tools in your browser.

### Tools

- https://redbot.org/
- https://securityheaders.com/
- https://www.webpagetest.org/

## HTTP response body

View page source in your browser.

> [!IMPORTANT]
> Check Web Console for JavaScript errors.

### Tools

- https://validator.w3.org/
- https://www.webpagetest.org/

## PHP code

Dump triggered hooks (actions and filters) to a file.  
Copy [this MU plugin][debug-hooks] to `wp-content/mu-plugins/`.  
Follow the log: `tail -f wp-content/debug-hooks.log`

Alternatively enable debugging in wp-config.
```php
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);
define('WP_DEBUG_DISPLAY', false);
ini_set('display_errors', '0');
```
Follow the log: `tail -f wp-content/debug.log`

### Tools

- Plugin Identifier Search https://plugintests.com/search-ids

## PHP errors

Follow PHP error log: `tail -f error_log`

## Outbound HTTP requests

Log requests and responses.

### Tools

- `snitch` plugin
- `log-http-requests` plugin

## Cron events

Cron can be web-based and CLI-based.

Log events and failures.

## Background queue jobs

Check Action Scheduler logs.

## Database queries

Log queries before they are executed, see `EXPLAIN` statement.  
Copy [this snippet][debug-queries] to `wp-includes/class-wpdb.php`.  
Follow the log: `tail -f wp-content/debug-queries.log`

Log failed queries.

### Tools

- `index-wp-mysql-for-speed` plugin
- [Database Performance tuning][db-performance]

## Emails

Log sent emails and sending failures.

## Support my work

Please consider supporting my work as these lists take years to compile.

[![Sponsor][sponsor-button]][sponsors-page]

Thank you!

## General debug tools

- `query-monitor` plugin
- [Test Mode](https://github.com/szepeviktor/test-mode) plugin
- `airplane-mode` plugin
- `whats-running` plugin
- `frontend-debugger` plugin
- https://themecheck.info/

[debug-post-requests]: https://github.com/szepeviktor/wordpress-website-lifecycle/blob/master/debug/debug-post-requests.php
[debug-hooks]: https://github.com/szepeviktor/wordpress-website-lifecycle/blob/master/debug/debug-hooks.php
[debug-queries]: https://github.com/szepeviktor/wordpress-website-lifecycle/blob/master/debug/debug-queries.php
[sponsor-button]: https://github.com/szepeviktor/.github/raw/master/.github/assets/github-like-sponsor-button.svg
[sponsors-page]: https://github.com/sponsors/szepeviktor
[db-performance]: https://github.com/szepeviktor/debian-server-tools/blob/master/mysql/SQL-Performance.md
