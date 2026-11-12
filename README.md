# Forma

Open index.html to preview. Edit index.html for content and style.css for the design. Upload these files and .nojekyll to the root of a GitHub repository. In Settings → Pages choose Deploy from a branch, then main and /(root).

## Domain and security

1. Use a domain you control. Verify it in your GitHub account’s Pages settings, then add it in the repository’s Pages settings before pointing DNS there. Follow GitHub’s record instructions for your chosen apex domain or subdomain. After the certificate is provisioned, turn on Enforce HTTPS and verify HTTPS and the HTTP redirect.
2. If HSTS, managed WAF rules and DDoS controls are required on the custom hostname, configure an edge provider such as Cloudflare. Confirm the GitHub origin certificate works before enabling Full (strict) and proxying the hostname. Enable HSTS after verifying HTTPS works, then verify the Strict-Transport-Security response header and review edge security events. Edge controls protect traffic that passes through the proxy.
3. Protect publishing access with GitHub MFA, a unique strong password or passkey, and securely stored recovery codes. Limit repository and DNS permissions, review account access and keep a separate repository backup. Test a restore into a temporary checkout. Set up an external HTTPS uptime check and review security advisories and DNS changes.
4. Keep secrets and private files outside the publish directory. This starter has no CMS, JavaScript, form, database, or accounts. Its content security policy blocks scripts and form submissions. If you add accounts or data, use managed authentication with MFA and secure recovery, validate input server-side, encode output by context, use parameterized queries and least-privilege database roles, encrypt stored data and backups, and test recovery. Patch dependencies and scan for vulnerabilities once you add them.

GitHub custom-domain guide: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
