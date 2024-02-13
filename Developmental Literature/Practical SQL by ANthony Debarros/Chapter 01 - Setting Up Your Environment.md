#SQL #mysql #postgresql #databases #code-environment #dev-environemtn #development-environment 

$$Proper Planning Prevents Poor Performance...$$

# Chapter Summary 
---
*This chapter primarily focuses on setting up a proper code and development environment. We will be focusing on all of the necessary components that we need to have prepared to effectively run sql environments from our computer... 

## Installing A Text Editor 

- [I] Until  i make the switch over to NeoVIm (which I am cdertainly planning to do), I will be using the *==sublime text editor==*... 

## Installing PostgreSQL & pgAdmin 

*To install the following applications, follow the codeblock instructions listed below... 

[Step 01] 
*First We Need To Update Our System Via The Appropriate Package Manager... Since I am currently running Debian, I will need to use the APT package manager update commands...* 
```bash
sudo apt update && sudo apt full-upgrade 
```

*000. Directory Index 

*The following command will install PostgreSQL to our system...*
```bash
sudo apt install postgresql && sudo apt update
```

- [i] The database service is automatically configured with viable defaults, but can be customised based on your specific needs.
- [i] For additional information on configuring PostgreSQL see the literature by following this link >>> [[Chapter 01 - Setting Up Your Environment#Additional Configuration For PostgreSQL Post Install]]

[Step 02] 
*Now we need to install the latest version of pgAdmin... To do this on an Ubuntu System, we must use the proper repositories. To set them up on your local Ubuntu system, follow the commands shown below: 
```bash
curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
```

[Step 03] 
*Now we need to create our pgAdmin configuration file with the following command: 
```bash
sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

[Step 04] 
*Now we need to install pgAdmin itself, and afterwards, we will want to update and upgrade our system to endsure all installed components are up to date...*
```bash
sudo apt install pgadmin4
```

*For Web Version only of pgAdmin, follow this command alternatively:*
```bash
sudo apt install pgadmin4-web
```

*For Desktop Version only of pgAdmin, follow this command alternatively: 
```bash 
sudo apt install pgadmin4-desktop
```

>The top installation commnand previously shown, will install both the web version and desktop version of pgAdmin...

[Step 05]
*Finally, to finish the process, we will just want to check our versions of installed applications, with the following command:*
```bash
psql -V #This is to check the version of postgresql we have installed on our system...
```
*Terminal Output*
```bash
psql (PostgreSQL) 15.5 (Ubuntu 15.5-0ubuntu0.23.10.1)
```
*We already know based on the package name, that we are running the most current pgAdmin Version 4 on our system... 

- [i] If you are worried you don't have the newest version, simply launch the application in desktop mode, click on the about dropdown, and view the version there... 

>About pgAdmin 4
- Version= 8.3
- Application Mode= Desktop
- Current User= pgadmin4@pgadmin.org
- NW.js Version= 0.77.0
- Browser= Chromium 114.0.5735.91
- Operating System= Linux-6.5.0-17-generic-x86_64-with-glibc2.38
- pgAdmin Database File= /home/archn3m3sis/.pgadmin/pgadmin4.db
- Log File/home/archn3m3sis/.pgadmin/pgadmin4.log

>Server Configuration
- *Below is the server configuration which can be found in the about section of the pgAdmin desktop application..*. 
```pgAdmin-server-config
ALLOW_SAVE_PASSWORD = True
ALLOW_SAVE_TUNNEL_PASSWORD = False
APP_COPYRIGHT = "Copyright (C) 2013 - 2024, The pgAdmin Development Team"
APP_ICON = "pg-icon"
APP_NAME = "pgAdmin 4"
APP_RELEASE = 8
APP_REVISION = 3
APP_SUFFIX = ""
APP_VERSION = "8.3"
APP_VERSION_EXTN = ('.css', '.js', '.html', '.svg', '.png', '.gif', '.ico')
APP_VERSION_INT = 80300
APP_VERSION_PARAM = "ver"
AUTHENTICATION_SOURCES = ['internal']
AUTO_DISCOVER_SERVERS = True
AZURE_CREDENTIAL_CACHE_DIR = "/home/archn3m3sis/.pgadmin/azurecredentialcache"
CA_FILE = "/usr/pgadmin4/web/cacert.pem"
CHECK_EMAIL_DELIVERABILITY = False
CHECK_SESSION_FILES_INTERVAL = 24
CHECK_SUPPORTED_BROWSER = True
COMPRESS_LEVEL = 9
COMPRESS_MIMETYPES = ['text/html', 'text/css', 'text/xml', 'text/javascript', 'application/json', 'application/javascript']
COMPRESS_MIN_SIZE = 500
CONFIG_DATABASE_CONNECTION_MAX_OVERFLOW = 100
CONFIG_DATABASE_CONNECTION_POOL_SIZE = 5
CONFIG_DATABASE_URI = ""
CONSOLE_LOG_FORMAT = "%(asctime)s: %(levelname)s	%(name)s:	%(message)s"
CONSOLE_LOG_LEVEL = 30
CONTENT_SECURITY_POLICY = "default-src ws: http: data: blob: 'unsafe-inline' 'unsafe-eval';"
COOKIE_DEFAULT_DOMAIN = None
COOKIE_DEFAULT_PATH = "/"
DATA_DIR = "/home/archn3m3sis/.pgadmin"
DEBUG = False
DEFAULT_BINARY_PATHS = {'pg': '/usr/bin', 'ppas': ''}
DEFAULT_SERVER = "127.0.0.1"
DEFAULT_SERVER_PORT = 5050
DESKTOP_USER = "pgadmin4@pgadmin.org"
DISABLED_LOCAL_PASSWORD_STORAGE = False
EFFECTIVE_SERVER_PORT = 40939
ENABLE_BINARY_PATH_BROWSING = False
ENABLE_PSQL = True
ENABLE_SERVER_PASS_EXEC_CMD = False
ENHANCED_COOKIE_PROTECTION = True
FILE_LOG_FORMAT = "%(asctime)s: %(levelname)s	%(name)s:	%(message)s"
FILE_LOG_LEVEL = 30
HELP_PATH = "../../../share/docs/en_US/html/"
IS_WIN = False
KERBEROS_CCACHE_DIR = "/home/archn3m3sis/.pgadmin/krbccache"
KEYRING_NAME = "SecretService Keyring"
KRB_APP_HOST_NAME = "127.0.0.1"
KRB_AUTO_CREATE_USER = True
KRB_KTNAME = "<KRB5_KEYTAB_FILE>"
LANGUAGES = {'en': 'English', 'zh': 'Chinese (Simplified)', 'cs': 'Czech', 'fr': 'French', 'de': 'German', 'id': 'Indonesian', 'it': 'Italian', 'ja': 'Japanese', 'ko': 'Korean', 'pl': 'Polish', 'pt_BR': 'Portuguese (Brazilian)', 'ru': 'Russian', 'es': 'Spanish'}
LDAP_ANONYMOUS_BIND = False
LDAP_AUTO_CREATE_USER = True
LDAP_BASE_DN = "<Base-DN>"
LDAP_BIND_FORMAT = "{LDAP_USERNAME_ATTRIBUTE}={LDAP_USERNAME},{LDAP_BASE_DN}"
LDAP_BIND_USER = None
LDAP_CA_CERT_FILE = ""
LDAP_CERT_FILE = ""
LDAP_CONNECTION_TIMEOUT = 10
LDAP_DN_CASE_SENSITIVE = False
LDAP_IGNORE_MALFORMED_SCHEMA = False
LDAP_KEY_FILE = ""
LDAP_SEARCH_BASE_DN = "<Search-Base-DN>"
LDAP_SEARCH_FILTER = "(objectclass=*)"
LDAP_SEARCH_SCOPE = "SUBTREE"
LDAP_SERVER_URI = "ldap://<ip-address>:<port>"
LDAP_USERNAME_ATTRIBUTE = "<User-id>"
LDAP_USE_STARTTLS = False
LOGIN_ATTEMPT_FIELDS = ['password']
LOGIN_BANNER = ""
LOG_FILE = "/home/archn3m3sis/.pgadmin/pgadmin4.log"
LOG_ROTATION_AGE = 1440
LOG_ROTATION_MAX_LOG_FILES = 90
LOG_ROTATION_SIZE = 10
MAIL_DEBUG = False
MAIL_PORT = 25
MAIL_SERVER = "localhost"
MAIL_USERNAME = ""
MAIL_USE_SSL = False
MAIL_USE_TLS = False
MASTER_PASSWORD_HOOK = None
MASTER_PASSWORD_REQUIRED = True
MAX_LOGIN_ATTEMPTS = 3
MAX_QUERY_HIST_STORED = 20
MAX_SESSION_IDLE_TIME = 60
MFA_EMAIL_SUBJECT = None
MFA_ENABLED = False
MFA_FORCE_REGISTRATION = False
MFA_SUPPORTED_METHODS = ['email', 'authenticator']
MODULE_BLACKLIST = ['test']
NODE_BLACKLIST = []
OAUTH2_AUTO_CREATE_USER = True
OAUTH2_CONFIG = [{'OAUTH2_NAME': None, 'OAUTH2_DISPLAY_NAME': '<Oauth2 Display Name>', 'OAUTH2_CLIENT_ID': None, 'OAUTH2_CLIENT_SECRET': None, 'OAUTH2_TOKEN_URL': None, 'OAUTH2_AUTHORIZATION_URL': None, 'OAUTH2_SERVER_METADATA_URL': None, 'OAUTH2_API_BASE_URL': None, 'OAUTH2_USERINFO_ENDPOINT': None, 'OAUTH2_SCOPE': None, 'OAUTH2_USERNAME_CLAIM': None, 'OAUTH2_ICON': None, 'OAUTH2_BUTTON_COLOR': None, 'OAUTH2_ADDITIONAL_CLAIMS': None, 'OAUTH2_SSL_CERT_VERIFICATION': True}]
ON_DEMAND_RECORD_COUNT = 1000
OVERRIDE_USER_INACTIVITY_TIMEOUT = True
PASSWORD_LENGTH_MIN = 6
PG_DEFAULT_DRIVER = "psycopg3"
PROXY_X_FOR_COUNT = 1
PROXY_X_HOST_COUNT = 0
PROXY_X_PORT_COUNT = 1
PROXY_X_PREFIX_COUNT = 0
PROXY_X_PROTO_COUNT = 1
SECURITY_EMAIL_SENDER = "no-reply@localhost"
SECURITY_EMAIL_SUBJECT_PASSWORD_CHANGE_NOTICE = "Your password for pgAdmin 4 has been changed"
SECURITY_EMAIL_SUBJECT_PASSWORD_NOTICE = "Your pgAdmin 4 password has been reset"
SECURITY_EMAIL_SUBJECT_PASSWORD_RESET = "Password reset instructions for pgAdmin 4"
SECURITY_EMAIL_VALIDATOR_ARGS = {'check_deliverability': False}
SEND_FILE_MAX_AGE_DEFAULT = 31556952
SERVER_HEARTBEAT_TIMEOUT = 30
SERVER_MODE = False
SESSION_COOKIE_DOMAIN = None
SESSION_COOKIE_HTTPONLY = True
SESSION_COOKIE_NAME = "pga4_session"
SESSION_COOKIE_PATH = "/"
SESSION_COOKIE_SAMESITE = "Lax"
SESSION_COOKIE_SECURE = False
SESSION_DB_PATH = "/home/archn3m3sis/.pgadmin/sessions"
SESSION_EXPIRATION_TIME = 7
SESSION_SKIP_PATHS = ['/misc/ping']
SETTINGS_SCHEMA_VERSION = 39
SHARED_STORAGE = []
SHOW_GRAVATAR_IMAGE = True
SQLALCHEMY_TRACK_MODIFICATIONS = False
SQLITE_PATH = "/home/archn3m3sis/.pgadmin/pgadmin4.db"
SQLITE_TIMEOUT = 500
STORAGE_DIR = "/home/archn3m3sis/.pgadmin/storage"
STRICT_TRANSPORT_SECURITY = "max-age=31536000; includeSubDomains"
STRICT_TRANSPORT_SECURITY_ENABLED = False
SUPPORT_SSH_TUNNEL = True
TEST_SQLITE_PATH = "/home/archn3m3sis/.pgadmin/test_pgadmin4.db"
THREADED_MODE = True
UPGRADE_CHECK_ENABLED = True
UPGRADE_CHECK_KEY = "pgadmin4"
UPGRADE_CHECK_URL = "https://www.pgadmin.org/versions.json"
USER_INACTIVITY_TIMEOUT = 0
WEBSERVER_AUTO_CREATE_USER = True
WEBSERVER_REMOTE_USER = "REMOTE_USER"
WEB_SERVER = "Python"
WTF_CSRF_HEADERS = ['X-pgA-CSRFToken']
X_CONTENT_TYPE_OPTIONS = "nosniff"
X_FRAME_OPTIONS = "SAMEORIGIN"
X_XSS_PROTECTION = "1; mode=block"
```
### Additional Necessary Components To Use PostgreSQL and pgAdmin
---
```bash 
sudo apt install postgresql-postgis
```

```bash
sudo apt install postgresql-plpython3
```

# Alternative PostgreSQL Installation Instructions Drirectly From The PostgreSQL Webpage... 

[Linux Download Link](https://www.postgresql.org/media/img/debian.svg)

PostgreSQL is available in all Debian versions by default. However, the stable versions of Debians "snapshot" a specific version of PostgreSQL that is then supported throughout the lifetime of that Debian version. The PostgreSQL project also maintains an [apt repository](https://www.postgresql.org/download/linux/debian/#apt) with all supported of PostgreSQL available.

## PostgreSQL Apt Repository

If the version included in your version of Debian is not the one you want, you can use the [PostgreSQL Apt Repository](https://apt.postgresql.org). This repository will integrate with your normal systems and patch management, and provide automatic updates for all supported versions of PostgreSQL throughout the support [lifetime](https://www.postgresql.org/support/versioning/) of PostgreSQL.

The PostgreSQL apt repository supports the currently supported stable versions of Debian:

- bookworm (12.x)
- bullseye (11.x)
- buster (10.x)
- sid (unstable)

on the following architectures:

- amd64
- arm64
- i386 (buster and older)
- ppc64el

To use the apt repository, follow these steps:

# Create the file repository configuration:
sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

# Import the repository signing key:
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

# Update the package lists:
sudo apt-get update

# Install the latest version of PostgreSQL.
# If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':
sudo apt-get -y install postgresql

For more information about the apt repository, including answers to frequent questions, please see the apt page on [the wiki](https://wiki.postgresql.org/wiki/Apt).

## Included in distribution

Debian includes PostgreSQL by default. To install PostgreSQL on Debian, use the `apt-get` (or other apt-driving) command:

  apt-get install postgresql-12

The repository contains many different packages including third party addons. The most common and important packages are (substitute the version number as required):

|   |   |
|---|---|
|postgresql-client-12|client libraries and client binaries|
|postgresql-12|core database server|
|libpq-dev|libraries and headers for C language frontend development|
|postgresql-server-dev-12|libraries and headers for C language backend development|

## Fixing PostgreSQL Issues With Client Authentication Post Install 
*PostgreSQL now defaults to a configuration that would not allow immediate connection to your server on the local system...

*This is a frustrating scenario due to the fact that you are trying to set up a proigram to become familiar with it and yet you are not even able to start actively using the application to become better at it! 

[The folliowiing Steps SHould Help You Fix The Issue]
1. Change the authentication method(s) defined in your `pg_hba.conf` file to `trust`, `md5`, or `password` (depending on your security and simplicity needs) for the local connection records you have defined in there.
2. Update `pg_ident.conf` to map your operating system users to PostgreSQL users and grant them the corresponding access privileges, depending on your needs.
3. Leave the IDENT settings alone and create users in your database for each operating system user that you want to grant access to. If a user is already authenticated by the OS and logged in, PostgreSQL won't require further authentication and will grant access to that user based on whatever privileges (roles) are assigned to it in the database. This is the default configuration.

PORT 22       -    TCP - OPEN - SSH
PORT 80       -    TCP - OPEN - HTTP
PORT 443     -    TCP - OPEN - HTTPS
PORT 631     -    TCP - OPEN - IPP
PORT 902     -    TCP - OPEN - ISS-REALSECURE
PORT 1025   -    TCP - OPEN - NFS-OR-IIS
PORT 5432   -    TCP - OPEN - POSTGRESQL
PORT 9000   -    TCP - OPEN - CSLISTENER



```bash
sudo nmap localhost                       
```

```bash
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-02-11 15:40 EST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.0000060s latency).
Not shown: 993 closed tcp ports (reset)
```

*Netstat Command Input To View Active or Listening Services*
```bash
netstat -tlpdn
```


*Output From Netstat Command Run As Archn3m3sis*
```bash
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:1025          0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 127.0.0.1:1143          0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:6341          0.0.0.0:*               LISTEN      6445/megasync       
tcp        0      0 127.0.0.1:5432          0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:9443            0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:9000            0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:43273         0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 0.0.0.0:902             0.0.0.0:*               LISTEN      -                   
tcp6       0      0 ::1:631                 :::*                    LISTEN      -                   
tcp6       0      0 :::60000                :::*                    LISTEN      -                   
tcp6       0      0 :::9443                 :::*                    LISTEN      -                   
tcp6       0      0 :::9000                 :::*                    LISTEN      -                   
tcp6       0      0 :::22                   :::*                    LISTEN      -                   
tcp6       0      0 :::80                   :::*                    LISTEN      -                   
tcp6       0      0 :::902                  :::*                    LISTEN      -     
```


```bash
sudo netstat -tlpdn
```


```bash
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:1025          0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 127.0.0.1:1143          0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      2259/cupsd          
tcp        0      0 127.0.0.1:6341          0.0.0.0:*               LISTEN      6445/megasync       
tcp        0      0 127.0.0.1:5432          0.0.0.0:*               LISTEN      2349/postgres       
tcp        0      0 0.0.0.0:9443            0.0.0.0:*               LISTEN      3636/docker-proxy   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      1515/systemd-resolv 
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      1515/systemd-resolv 
tcp        0      0 0.0.0.0:9000            0.0.0.0:*               LISTEN      3655/docker-proxy   
tcp        0      0 127.0.0.1:43273         0.0.0.0:*               LISTEN      5100/bridge         
tcp        0      0 0.0.0.0:902             0.0.0.0:*               LISTEN      3396/vmware-authdla 
tcp6       0      0 ::1:631                 :::*                    LISTEN      2259/cupsd          
tcp6       0      0 :::60000                :::*                    LISTEN      2451/ipp-usb        
tcp6       0      0 :::9443                 :::*                    LISTEN      3643/docker-proxy   
tcp6       0      0 :::9000                 :::*                    LISTEN      3661/docker-proxy   
tcp6       0      0 :::22                   :::*                    LISTEN      1/init              
tcp6       0      0 :::80                   :::*                    LISTEN      2345/apache2        
tcp6       0      0 :::902                  :::*                    LISTEN      3396/vmware-authdla 
```


```bash
sudo iptables -S
```

```bash
-P INPUT DROP
-P FORWARD DROP
-P OUTPUT ACCEPT
-N DOCKER
-N DOCKER-ISOLATION-STAGE-1
-N DOCKER-ISOLATION-STAGE-2
-N DOCKER-USER
-N ufw-after-forward
-N ufw-after-input
-N ufw-after-logging-forward
-N ufw-after-logging-input
-N ufw-after-logging-output
-N ufw-after-output
-N ufw-before-forward
-N ufw-before-input
-N ufw-before-logging-forward
-N ufw-before-logging-input
-N ufw-before-logging-output
-N ufw-before-output
-N ufw-logging-allow
-N ufw-logging-deny
-N ufw-not-local
-N ufw-reject-forward
-N ufw-reject-input
-N ufw-reject-output
-N ufw-skip-to-policy-forward
-N ufw-skip-to-policy-input
-N ufw-skip-to-policy-output
-N ufw-track-forward
-N ufw-track-input
-N ufw-track-output
-N ufw-user-forward
-N ufw-user-input
-N ufw-user-limit
-N ufw-user-limit-accept
-N ufw-user-logging-forward
-N ufw-user-logging-input
-N ufw-user-logging-output
-N ufw-user-output
-A INPUT -j ufw-before-logging-input
-A INPUT -j ufw-before-input
-A INPUT -j ufw-after-input
-A INPUT -j ufw-after-logging-input
-A INPUT -j ufw-reject-input
-A INPUT -j ufw-track-input
-A FORWARD -j DOCKER-USER
-A FORWARD -j DOCKER-ISOLATION-STAGE-1
-A FORWARD -o docker0 -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
-A FORWARD -o docker0 -j DOCKER
-A FORWARD -i docker0 ! -o docker0 -j ACCEPT
-A FORWARD -i docker0 -o docker0 -j ACCEPT
-A FORWARD -j ufw-before-logging-forward
-A FORWARD -j ufw-before-forward
-A FORWARD -j ufw-after-forward
-A FORWARD -j ufw-after-logging-forward
-A FORWARD -j ufw-reject-forward
-A FORWARD -j ufw-track-forward
-A OUTPUT -j ufw-before-logging-output
-A OUTPUT -j ufw-before-output
-A OUTPUT -j ufw-after-output
-A OUTPUT -j ufw-after-logging-output
-A OUTPUT -j ufw-reject-output
-A OUTPUT -j ufw-track-output
-A DOCKER -d 172.17.0.2/32 ! -i docker0 -o docker0 -p tcp -m tcp --dport 9443 -j ACCEPT
-A DOCKER -d 172.17.0.2/32 ! -i docker0 -o docker0 -p tcp -m tcp --dport 9000 -j ACCEPT
-A DOCKER-ISOLATION-STAGE-1 -i docker0 ! -o docker0 -j DOCKER-ISOLATION-STAGE-2
-A DOCKER-ISOLATION-STAGE-1 -j RETURN
-A DOCKER-ISOLATION-STAGE-2 -o docker0 -j DROP
-A DOCKER-ISOLATION-STAGE-2 -j RETURN
-A DOCKER-USER -j RETURN
-A ufw-after-input -p udp -m udp --dport 137 -j ufw-skip-to-policy-input
-A ufw-after-input -p udp -m udp --dport 138 -j ufw-skip-to-policy-input
-A ufw-after-input -p tcp -m tcp --dport 139 -j ufw-skip-to-policy-input
-A ufw-after-input -p tcp -m tcp --dport 445 -j ufw-skip-to-policy-input
-A ufw-after-input -p udp -m udp --dport 67 -j ufw-skip-to-policy-input
-A ufw-after-input -p udp -m udp --dport 68 -j ufw-skip-to-policy-input
-A ufw-after-input -m addrtype --dst-type BROADCAST -j ufw-skip-to-policy-input
-A ufw-after-logging-forward -m limit --limit 3/min --limit-burst 10 -j LOG --log-prefix "[UFW BLOCK] "
-A ufw-after-logging-input -m limit --limit 3/min --limit-burst 10 -j LOG --log-prefix "[UFW BLOCK] "
-A ufw-before-forward -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
-A ufw-before-forward -p icmp -m icmp --icmp-type 3 -j ACCEPT
-A ufw-before-forward -p icmp -m icmp --icmp-type 11 -j ACCEPT
-A ufw-before-forward -p icmp -m icmp --icmp-type 12 -j ACCEPT
-A ufw-before-forward -p icmp -m icmp --icmp-type 8 -j ACCEPT
-A ufw-before-forward -j ufw-user-forward
-A ufw-before-input -i lo -j ACCEPT
-A ufw-before-input -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
-A ufw-before-input -m conntrack --ctstate INVALID -j ufw-logging-deny
-A ufw-before-input -m conntrack --ctstate INVALID -j DROP
-A ufw-before-input -p icmp -m icmp --icmp-type 3 -j ACCEPT
-A ufw-before-input -p icmp -m icmp --icmp-type 11 -j ACCEPT
-A ufw-before-input -p icmp -m icmp --icmp-type 12 -j ACCEPT
-A ufw-before-input -p icmp -m icmp --icmp-type 8 -j ACCEPT
-A ufw-before-input -p udp -m udp --sport 67 --dport 68 -j ACCEPT
-A ufw-before-input -j ufw-not-local
-A ufw-before-input -d 224.0.0.251/32 -p udp -m udp --dport 5353 -j ACCEPT
-A ufw-before-input -d 239.255.255.250/32 -p udp -m udp --dport 1900 -j ACCEPT
-A ufw-before-input -j ufw-user-input
-A ufw-before-output -o lo -j ACCEPT
-A ufw-before-output -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
-A ufw-before-output -j ufw-user-output
-A ufw-logging-allow -m limit --limit 3/min --limit-burst 10 -j LOG --log-prefix "[UFW ALLOW] "
-A ufw-logging-deny -m conntrack --ctstate INVALID -m limit --limit 3/min --limit-burst 10 -j RETURN
-A ufw-logging-deny -m limit --limit 3/min --limit-burst 10 -j LOG --log-prefix "[UFW BLOCK] "
-A ufw-not-local -m addrtype --dst-type LOCAL -j RETURN
-A ufw-not-local -m addrtype --dst-type MULTICAST -j RETURN
-A ufw-not-local -m addrtype --dst-type BROADCAST -j RETURN
-A ufw-not-local -m limit --limit 3/min --limit-burst 10 -j ufw-logging-deny
-A ufw-not-local -j DROP
-A ufw-skip-to-policy-forward -j DROP
-A ufw-skip-to-policy-input -j DROP
-A ufw-skip-to-policy-output -j ACCEPT
-A ufw-track-output -p tcp -m conntrack --ctstate NEW -j ACCEPT
-A ufw-track-output -p udp -m conntrack --ctstate NEW -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 443 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 443 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 5432 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 5432 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 9000 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 9000 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 1025 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 1025 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 902 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 902 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 631 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 631 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 80 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 80 -j ACCEPT
-A ufw-user-input -p tcp -m tcp --dport 22 -j ACCEPT
-A ufw-user-input -p udp -m udp --dport 22 -j ACCEPT
-A ufw-user-limit -m limit --limit 3/min -j LOG --log-prefix "[UFW LIMIT BLOCK] "
-A ufw-user-limit -j REJECT --reject-with icmp-port-unreachable
-A ufw-user-limit-accept -j ACCEPT
```


#### Solution For pgAdmin Authentication Failures
*The following command tells our system to behave as if the user input after the i is logged into the system...
```bash
sudo -i -u postgres
```
*The following command will allow you to set a new default password for PostgreSQL user... 
```psql
\password
```
*After entering the above command into the terminal (Ensure you are inside of a postgres instance when doing so!) you should be prompted to enter a new default password... Once you have completed this, go back to pgAdmin4 and attempt to create an initial; default server once again...

>Once all of this has been completed you should be up and running with pgAdmin


### Exploring The PostgreSQL Query Tool In pgAdmin
---
The `Query Tool` allows you to write and execute code for your SQL database... 

*Once you have access the query tool, you will be running your first command inside of it.... The command in SQL to retrieve the servers versioning is as follows: 

```sql 
SELECT version();
```


>Before moving any further, we need to download some supplemental resources from our reading... Lets go to the No Starch Press Website @:

[No Starch Press Webpage](https://www.nostarch.com/practical-sql-2nd-edition/)

[No Starch Press Github Resource Link](https://github.com/anthonydb/practical-sql-2/)

```bash
git clone https://github.com/anthonydb/practical-sql-2.git
```










































### Additional Configuration For PostgreSQL Post Install 
---
## Configuration

PostgreSQL supports multiple client authentication methods. In Ubuntu, `peer` is the default authentication method used for `local` connections, while `scram-sha-256` is the default for `host` connections (this used to be `md5` until Ubuntu 21.10). Please refer to the [PostgreSQL Administrator’s Guide](http://www.postgresql.org/docs/current/static/admin.html) if you would like to configure alternatives like Kerberos.

The following discussion assumes that you wish to enable TCP/IP connections and use the MD5 method for client authentication. PostgreSQL configuration files are stored in the `/etc/postgresql/<version>/main` directory. For example, if you install PostgreSQL 14, the configuration files are stored in the `/etc/postgresql/14/main` directory.

> **Tip**:  
> To configure _IDENT_ authentication, add entries to the `/etc/postgresql/*/main/pg_ident.conf` file. There are detailed comments in the file to guide you.

By default only connections from the local system are allowed, to enable all other computers to connect to your PostgreSQL server, edit the file `/etc/postgresql/*/main/postgresql.conf`. Locate the line: _#listen_addresses = ‘localhost’_ and change it to `*`:

```
listen_addresses = '*'
```

> **Note**:  
> ‘*’ will allow all available IP interfaces (IPv4 and IPv6), to only listen for IPv4 set ‘0.0.0.0’ while ‘::’ allows listening for all IPv6 addresses.

For details on other parameters, refer to the configuration file or to the [PostgreSQL documentation](https://www.postgresql.org/docs/) for information on how they can be edited.

Now that we can connect to our PostgreSQL server, the next step is to set a password for the _postgres_ user. Run the following command at a terminal prompt to connect to the default PostgreSQL template database:

```
sudo -u postgres psql template1
```

The above command connects to PostgreSQL database _template1_ as user _postgres_. Once you connect to the PostgreSQL server, you will be at an SQL prompt. You can run the following SQL command at the `psql` prompt to configure the password for the user _postgres_.

```
ALTER USER postgres with encrypted password 'your_password';
```

After configuring the password, edit the file `/etc/postgresql/*/main/pg_hba.conf` to use _scram-sha-256_ authentication with the _postgres_ user, allowed for the template1 database, from any system in the local network (which in the example is 192.168.122.1/24) :

```
hostssl template1       postgres        192.168.122.1/24        scram-sha-256
```

> **Note**:  
> The config statement ‘hostssl’ used here will reject tcp connections that would not use ssl. Postgresql in Ubuntu has the ssl feature built in and configured by default, so it works right away. On your postgresql server this uses the certificate created by ‘ssl-cert’ package which is great, but for production use you should consider updating that with a proper certificate from a recognized CA.

Finally, you should restart the PostgreSQL service to initialise the new configuration. From a terminal prompt enter the following to restart PostgreSQL:

```
sudo systemctl restart postgresql.service
```

> **Warning**:  
> The above configuration is not complete by any means. Please refer to the [PostgreSQL Administrator’s Guide](http://www.postgresql.org/docs/current/static/admin.html) to configure more parameters.

You can test server connections from other machines by using the PostgreSQL client as follows, replacing the domain name with your actual server domain name or IP address:

```
sudo apt install postgresql-client
psql --host your-servers-dns-or-ip --username postgres --password --dbname template1
```

### Streaming replication

PostgreSQL has a nice feature called Streaming Replication which provides the capability to continuously ship and apply the Write-Ahead Log [(WAL) XLOG](http://www.postgresql.org/docs/current/static/wal.html) records to some number of standby servers in order to keep them current. Here is presented a very basic and simple way to replicate a PostgreSQL server (main) to a standby server.

First, create a replication user in the main server to be used from the standby server:

```
sudo -u postgres createuser --replication -P -e replicator
```

Let’s configure the main server to turn on the streaming replication. Open the file `/etc/postgresql/*/main/postgresql.conf` and make sure you have the following lines:

```
listen_addresses = '*'
wal_level = replica
```

Also edit the file `/etc/postgresql/*/main/pg_hba.conf` to add an extra line to allow the standby server connection for replication (that is a special keyword) using the `replicator` user:

```
host  replication   replicator   <IP address of the standby>      scram-sha-256
```

Restart the service to apply changes:

```
sudo systemctl restart postgresql
```

Now, in the standby server, let’s stop the PostgreSQL service:

```
sudo systemctl stop postgresql
```

Edit the `/etc/postgresql/*/main/postgresql.conf` to set up hot standby:

```
hot_standby = on
```

Back up the current state of the main server (those commands are still issued on the standby system):

```
sudo su - postgres
# backup the current content of the standby server (update the version of your postgres accordingly)
cp -R /var/lib/postgresql/14/main /var/lib/postgresql/14/main_bak
# remove all the files in the data directory
rm -rf /var/lib/postgresql/14/main/*
pg_basebackup -h <IP address of the main server> -D /var/lib/postgresql/14/main -U replicator -P -v -R
```

After the above this will have done a full single pass copying the content of the main database onto the local system being the standby. In the `pg_basebackup` command the flags represent the following:

- `-h`: The hostname or IP address of the main server
- `-D`: The data directory
- `-U`: The user to be used in the operation
- `-P`: Turns on progress reporting
- `-v`: Enables verbose mode
- `-R`: Creates a `standby.signal` file and appends connection settings to `postgresql.auto.conf`

Finally, let’s start the PostgreSQL service on standby server:

```
sudo systemctl start postgresql
```

To make sure it is working, go to the main server and run the following command:

```
sudo -u postgres psql -c "select * from pg_stat_replication;"
```

As mentioned, this is a very simple introduction, there are way more great details in the upstream documentation about the configuration of [replication](https://www.postgresql.org/docs/current/static/runtime-config-replication.html) as well as further [High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/static/high-availability.html).

To test the replication you can now create a test database in the main server and check if it is replicated in the standby server:

```
sudo -u postgres createdb test # on the main server
sudo -u postgres psql -c "\l" # on the standby server
```

You need to be able to see the `test` database, that was created on the main server, in the standby server.

## Backups

PostgreSQL databases should be backed up regularly. Refer to the [PostgreSQL Administrator’s Guide](http://www.postgresql.org/docs/current/static/backup.html) for different approaches.

## Resources

- As mentioned above, the [PostgreSQL Administrator’s Guide](http://www.postgresql.org/docs/current/static/admin.html) is an excellent resource. The guide is also available in the `postgresql-doc` package. Execute the following in a terminal to install the package:
    
    ```
    sudo apt install postgresql-doc
    ```
    

This package provides further man pages on postgresql ‘dblink’ and ‘server programming interface’ as well as the html guide that you’d find upstream. To view the guide enter `xdg-open /usr/share/doc/postgresql-doc-*/html/index.html` or point your browser at it.

- For general SQL information see the O’Reilly books [Getting Started with SQL: A Hands-On Approach for Beginners](http://shop.oreilly.com/product/0636920044994.do) by Thomas Nield as an entry point and [SQL in a Nutshell](http://shop.oreilly.com/product/9780596518851.do) as a quick reference.
    
- Also, see the [PostgreSQL Ubuntu Wiki](https://help.ubuntu.com/community/PostgreSQL) page for more information.
-