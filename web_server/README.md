# Web server

Ubuntu 16.04 LTS web server automation. Run configuration scripts as root.

| File | Purpose |
| --- | --- |
| 0-transfer_file | Transfer a file using four arguments and scp |
| 1-install_nginx_web_server | Install nginx and serve Holberton School on port 80 |
| 2-setup_a_domain_name | Root domain name only |
| 3-redirection | Install nginx and redirect /redirect_me to another page with HTTP 301 |
| 4-not_found_page_404 | Install nginx, preserve the redirect and serve a custom HTTP 404 |
| 5-design_a_beautiful_404_page.html | Illustrated paper-boat 404 page for manual review |

## Configure web01 after pushing

GitHub commits do not configure your server. Clone or update this repository on
web01, then run these commands there (not in Windows PowerShell):

```bash
cd alu-system_engineering-devops/web_server
sudo bash 4-not_found_page_404
curl -i http://localhost/
curl -I http://localhost/redirect_me/
curl -i http://localhost/missing-page
```

Configure an A record for d4vidfarm.tech pointing at the web01 IP listed in My servers.
Set this root domain in your intranet profile's Project website url field.
Allow DNS propagation time and verify the registrar is Dotserve Inc as required.

Task 5 needs personal customization and manual peer review. To serve the design,
copy it to /var/www/html/404.html on web01 after running task 4; the configuration
will retain HTTP 404 and the required phrase. Check it in a browser before review.

Run Shellcheck 0.3.7 on the four Bash scripts before submitting.
