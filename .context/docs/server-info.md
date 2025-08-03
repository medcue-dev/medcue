# Medcue Server Information

## Production Server
- **Host**: medcue-prod-01
- **OS**: Ubuntu 22.04 LTS  
- **Users**: medcue-app, medcue-admin
- **Services**: nginx, postgresql, redis

## Development Environment
- **Database**: PostgreSQL 14
- **Cache**: Redis 6
- **Web Server**: nginx with SSL

## Key Directories
- App code: `/var/www/medcue`
- Logs: `/var/log/medcue`
- Backups: `/opt/backups/medcue`