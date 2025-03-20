I'll help you troubleshoot the Laravel project accessibility issue. Let's go through the potential solutions step by step:

1. First, check if the Apache configuration allows external access:

```apache
# Edit httpd.conf or the relevant virtual host configuration
<Directory "C:/xampp/htdocs">
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Require all granted
</Directory>
```

2. Verify Windows Firewall settings:
- Open Windows Defender Firewall
- Allow incoming connections for Apache (port 80)
- You can add a new rule with:
```powershell
New-NetFirewallRule -DisplayName "Allow Apache" -Direction Inbound -Action Allow -Protocol TCP -LocalPort 80
```

3. Check Laravel's `.env` configuration:
```
APP_URL=http://195.201.241.58
```

4. Ensure Apache is listening on all interfaces:
```apache
# In httpd.conf
Listen 0.0.0.0:80
```

5. Check Laravel's public directory permissions:
```powershell
icacls "C:\xampp\htdocs\your-project\public" /grant "Everyone:(OI)(CI)F"
```

Could you please check these things and let me know:
1. Can you ping the VPS IP from other computers?
2. Are you getting any specific error message when accessing from other computers?
3. Is your hosting provider (appears to be Hetzner based on the IP) blocking any ports?

This will help me provide more specific guidance to resolve the issue.