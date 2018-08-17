# Nginx forward proxy

[Nginx](https://nginx.org/en/) is a very fast HTTP and reverse proxy server. 
Usually, Nginx is used to serve and cache static assets or as proxy or load balancer for incoming traffic to application servers. In this repository, it is used as forward proxy. 

## Use Case

Assume you have a network where you want to control outgoing traffic. 
You either want to: 

 - Deny all outgoing calls by default and only allow HTTP(S) calls to whitelisted URLs.
 - Allow all outgoing calls by default and only block HTTP(S) calls to blacklisted URLs.

The Docker daemon can be configured that way that it routes all traffic through an proxy. This proxy can be an Nginx which is configured as forwarding proxying.

## Google search query

**q=query+goes+here

The query string. Words are separated by + signs.

Everything from here on in is preceded by an & sign, as it's tagged on to the end. Here's where (if you have no girlfriend), things get interesting...

as_epq=query+goes+here

Results must include the query, in the word order displayed.

Shows as "query goes here"

as_oq="query+string"+goes+here

Results must include one or more of the words in this string. Basically, it's like a more advanced version of the one above, using an "or" filter. Thus, every result must have the main initial query, and one or more of the sets of terms in these strings.

Shows as "query string" OR goes OR here

as_eq=don't+include+these+words

Results must NOT include any words in this string.

Shows as -don't -include -these -words

num=xx

Controls the number of results shown. Must be a numeric value, and can be anything up to 100. Doesn't work with fractions. I've tried.

as_filetype=extension

Only returns results that end in .extension. Currently supports any input. Try it - make a file with a random extension, get it indexed and do a search. Also shows that as long as it validates to something, Google can and will index it. Something to think about...

Shows as filetype:extension

as_sitesearch=Example Domain

Limits results to just the site you choose.

Shows as site:example.com

as_qdr=x

Swap out x for the following to limit the search to only files first indexed in:

d - the previous 24 hours
w - the previous seven days
m - the previous month
y - past year
mn - the previous n number of months. So m2 would be the previous two, m3 would be three, and so on. Does work into double digits
as_rights=xxx

Limits the search to files/pages that have certain rights. The options are:

(cc_publicdomain|cc_attribute|cc_sharealike|cc_noncommercial|cc_nonderived) - free to use or share
(cc_publicdomain|cc_attribute|cc_sharealike|cc_nonderived).-(cc_noncommercial) - free to use or share, including commercially
(cc_publicdomain|cc_attribute|cc_sharealike|cc_noncommercial).-(cc_nonderived) - free to use, share, or modify
(cc_publicdomain|cc_attribute|cc_sharealike).-(cc_noncommercial|cc_nonderived) - free to use, share, or modify commercially
If you want to make up your own, put the bits you want in brackets, separated by pipe characters (|), and exclude the bits you don't by putting them in brackets, preceded by .- and again pipe-separated.

allintitle%3Asearch+terms

This is actually appended to the q= parameter, hence a search for fishing with the allintitle term "sea bass" would require the following query:

q=fishing+allintitle%3Asea+bass

Shows as allintitle:search terms

N.B. This also works with allintext to search page body text, allinurl for searching the URL, and allinanchor for finding sites that are linked to with certain anchor text.

nnn..yyyy

Like the allin parameters, this is actually appended to the q= parameter. What this does though is let you search for results between numeric ranges. For example, if you wanted to find documents with numbers between 15 and 100, you'd put in 15..100. Very useful for finding products in a price range, when combined with the site limiter. Works with $, £, and other such things.

Shows as query 15..100

%2Bterm

Again, this is appended to the q= parameter. The %2B is actually the + sign encoded, and will return results featuring only the term used, with no pluralisations, alternate tenses, or synonyms.

Shows as +term

~term

Another one that's appended to the q= parameter. Returns results for the term used and synonyms.

Shows as ~term

define%3Aword

Yet another q= parameter add-on. Returns definitions for the word you put in.

Shows as define:word

term * term two

And another q= parameter add-on. Returns results with listings that contain both words, with other words between them.

n+n2, n-n2, n/n2, n*n2, n^n2 and n% of n2

Google's calculator functions. They are, in order, add, subtract, divide, multiply, raise to the power of, and return x percentage of.

safe=active

Sets safe search to on. To turn it off, change active to images.

as_rq=Example Domain

Finds sites Google thinks are related to the URL you put in.

Shows as query related:example.com

as_lq=Example Domain

Finds sites that link to the URL you put in.

Shows as query link:example.com

newwindow=n

Opens clicked listings in a new window. Very useful for opening lots of documents at a time, for competitor research. Set to 1 to activate, and 0 to turn it off.

pws

Controls whether personalised search is on or not. Set to 1 to activate, and 0 to turn it off.

adtest=on

Turns off AdWords database connection, so your browsing won't show up as an impression, and will disable the URLs. Set to on to activate, and off to turn it off.

btnG=Search

Simulates a click on the normal Google results buttpm. Change to btnI to get the I'm Feeling Lucky button result.

ie=

Controls the input encoding settings. This defaults to UTF-8, and is worked out server-side, hence changing it doesn't do anything.

oe=

Controls the output encoding settings. Works in the same way as ie, so you can tinker away, but it won't do anything.

&hl=value

Changes the interface language. I won't list them all here, but you can find them all here.

lr=value

Limits the languages used to return results. Not hugely effective. That said, here's the list of all of them:

lang_ar - Arabic
lang_hy - Armenian
lang_be - Belarusian
lang_bg - Bulgarian
lang_ca - Catalan
lang_hr - Croatian
lang_cs - Czech
lang_da - Danish
lang_nl - Dutch
lang_en - English
lang_eo - Esperanto
lang_et - Estonian
lang_tl - Filipino
lang_fi - Finnish
lang_fr - French
lang_de - German
lang_el - Greek
lang_iw - Hebrew
lang_hu - Hungarian
lang_is - Icelandic
lang_id - Indonesian
lang_it - Italian
lang_ja - Japanese
lang_ko - Korean
lang_lv - Latvian
lang_lt - Lithuanian
lang_no - Norwegian
lang_fa - Persian
lang_pl - Polish
lang_pt - Portuguese
lang_ro - Romanian
lang_ru - Russian
lang_sr - Serbian
lang_sk - Slovak
lang_sl - Slovenian
lang_es - Spanish
lang_sv - Swedish
lang_th - Thai
lang_tr - Turkish
lang_uk - Ukrainian
lang_vi - Vietnamese
lang_zh-CN - Chinese Simplified
lang_zh-TW - Chinese Traditional
cr=countryXX

Limits the search results to pages/sites from certain locations. Change XX to any of the following, to limit the results:

AF - Afghanistan
AL - Albania
DZ - Algeria
AS - American Samoa
AD - Andorra
AO - Angola
AI - Anguilla
AQ - Antarctica
AG - Antigua and Barbuda
AR - Argentina
AM - Armenia
AW - Aruba
AU - Australia
AT - Austria
AZ - Azerbaijan
BS - Bahamas
BH - Bahrain
BD - Bangladesh
BB - Barbados
BY - Belarus
BE - Belgium
BZ - Belize
BJ - Benin
BM - Bermuda
BT - Bhutan
BO - Bolivia
BA - Bosnia and Herzegovina
BW - Botswana
BV - Bouvet Island
BR - Brazil
IO - British Indian Ocean Territory
BN - Brunei Darussalam
BG - Bulgaria
BF - Burkina Faso
BI - Burundi
KH - Cambodia
CM - Cameroon
CA - Canada
CV - Cape Verde
KY - Cayman Islands
CF - Central African Republic
TD - Chad
CL - Chile
CN - China
CX - Christmas Island
CC - Cocos (Keeling) Islands
CO - Colombia
KM - Comoros
CG - Congo
CD - Congo, Democratic Republic
CK - Cook Islands
CR - Costa Rica
CI - Cote d'Ivoire
HR - Croatia
CY - Cyprus
CZ - Czech Republic
DK - Denmark
DJ - Djibouti
DM - Dominica
DO - Dominican Republic
TL - East Timor
EC - Ecuador
EG - Egypt
SV - El Salvador
GQ - Equatorial Guinea
ER - Eritrea
EE - Estonia
ET - Ethiopia
FK - Falkland Islands (Malvinas)
FO - Faroe Islands
FJ - Fiji
FI - Finland
FR - France
GF - French Guiana
PF - French Polynesia
TF - French Southern Territories
GA - Gabon
GM - Gambia
GE - Georgia
DE - Germany
GH - Ghana
GI - Gibraltar
GR - Greece
GL - Greenland
GD - Grenada
GP - Guadeloupe
GU - Guam
GT - Guatemala
GN - Guinea
GW - Guinea-Bissau
GY - Guyana
HT - Haiti
HM - Heard and McDonald Islands
HN - Honduras
HK - Hong Kong
HU - Hungary
IS - Iceland
IN - India
ID - Indonesia
IQ - Iraq
IE - Ireland
IL - Israel
IT - Italy
JM - Jamaica
JP - Japan
JO - Jordan
KZ - Kazakhstan
KE - Kenya
KI - Kiribati
KW - Kuwait
KG - Kyrgyzstan
LA - Lao People's Democratic Republic
LV - Latvia
LB - Lebanon
LS - Lesotho
LR - Liberia
LY - Libya
LI - Liechtenstein
LT - Lithuania
LU - Luxembourg
MO - Macau
MK - Macedonia
MG - Madagascar
MW - Malawi
MY - Malaysia
MV - Maldives
ML - Mali
MT - Malta
MH - Marshall Islands
MQ - Martinique
MR - Mauritania
MU - Mauritius
YT - Mayotte
MX - Mexico
FM - Micronesia
MD - Moldova
MC - Monaco
MN - Mongolia
MS - Montserrat
MA - Morocco
MZ - Mozambique
NA - Namibia
NR - Nauru
NP - Nepal
NL - Netherlands
AN - Netherlands Antilles
NC - New Caledonia
NZ - New Zealand
NI - Nicaragua
NE - Niger
NG - Nigeria
NU - Niue
NF - Norfolk Island
MP - Northern Maria
a Islands
NO - Norway
OM - Oman
PK - Pakistan
PW - Palau
PS - Palestinian Territory
PA - Panama
PG - Papua New Guinea
PY - Paraguay
PE - Peru
PH - Philippines
PN - Pitcairn
PL - Poland
PT - Portugal
PR - Puerto Rico
QA - Qatar
RE - Reunion
RO - Romania
RU - Russian Federation
RW - Rwanda
KN - Saint Kitts and Nevis
LC - Saint Lucia
VC - Saint Vincent and the Grenadines
WS - Samoa
SM - San Marino
ST - Sao Tome and Principe
SA - Saudi Arabia
SN - Senegal
CS - Serbia and Montenegro
SC - Seychelles
SL - Sierra Leone
SG - Singapore
SK - Slovakia
SI - Slovenia
SB - Solomon Islands
SO - Somalia
ZA - South Africa
GS - South Georgia and The South Sandwich Islands
KR - South Korea
ES - Spain
LK - Sri Lanka
SH - St. Helena
PM - St. Pierre and Miquelon
SR - Suriname
SJ - Svalbard and Jan Mayen Islands
SZ - Swaziland
SE - Sweden
CH - Switzerland
TW - Taiwan
TJ - Tajikistan
TZ - Tanzania
TH - Thailand
TG - Togo
TK - Tokelau
TO - Tonga
TT - Trinidad and Tobago
TN - Tunisia
TR - Turkey
TM - Turkmenistan
TC - Turks and Caicos Islands
TV - Tuvalu
UG - Uganda
UA - Ukraine
AE - United Arab Emirates
GB - United Kingdom
US - United States
UM - United States Minor Outlying Islands
UY - Uruguay
UZ - Uzbekistan
VU - Vanuatu
VA - Vatican
VE - Venezuela
VN - Viet Nam
VG - Virgin Islands (British)
VI - Virgin Islands (U.S.)
WF - Wallis and Futuna Islands
EH - Western Sahara
YE - Yemen
ZM - Zambia
ZW - Zimbabwe
If you can think of anything I've missed, please add it**

## ngx\_http\_proxy\_connect\_module

Nginx is can be configured for forwarding proxying. 
Unfortunately, that doesn't work very well with HTTPS connections. 
As soon the user is calling a URL via https, Nginx will throw errors. 
There is a [StackOverflow issue](https://superuser.com/questions/604352/nginx-as-forward-proxy-for-https)
to that topic. Luckily there is a solution for that problem. 
The [ngx\_http\_proxy\_connect\_module](https://github.com/chobits/ngx_http_proxy_connect_module)
is solving this issue. If Nginx is compiled with that module, 
the proxying will work with SSL connections as well. 

*For the specific case, we will only  entertain the q=search term.* 

## Docker Build

The Dockerfile in this repository is assembling an Nginx with the [ngx\_http\_proxy\_connect\_module](https://github.com/chobits/ngx_http_proxy_connect_module)
and an nginx.conf file which blocks all outgoing traffic by default, 
but allows access to some whitelisted domains like google.com.
The Docker image can be built like this: 

```
docker build -t reiz/nginx_proxy:0.0.1 . 
```

Or simply download it from [Docker Hub](https://hub.docker.com/r/reiz/nginx_proxy/) with: 

```
docker pull reiz/nginx_proxy:latest
```
**Currently, the docker base image is ubuntu 16.04. It is still going to  come with all the package you do not necessary need it. Personally, I agree with Alpine linux model with the very bare bone approach, you will worry less about updates and unnecessary packages that you will never need. For that sense, you will worry less for your security too. Additionally, the build should be in the continous build, so when code changes, it will build automatically to catch any issue. The image should be pushed to a docker repository along the process. A shell script for that purpose should be created.**

  ## ToDo
  ** Use Alpine linux base image
  ** Use APK to install packages. 

## Whitelist certain domains

This repository contains two nginx configuration files. 
The `nginx_whitelist.conf` file is built for the use case that you want to deny all outgoing traffic by default and only allow some whitelisted domains. 
In the first server section domains can be whitelisted by simply adding a 
`server_name *` line for each whitelisted domain. Here an example: 

```
    # Whitelist Google
    server {
        listen       8888;
        server_name  google.com;
        server_name  *.google.com;
        server_name  google.de;
        server_name  www.google.de;
        proxy_connect;
        proxy_max_temp_file_size 0;
        resolver 8.8.8.8;
        location / {
           proxy_pass http://$http_host;
           proxy_set_header Host $http_host;
        }
    }
```

Regex can be used to describe a domain. This `*.google.com` for example is whitelisting all subdomains of google.com. In the above example, google.com and all subdomains of it are whitelisted. Beside that google.de and www.google.de are whitelisted. Subdomains of google.de are **not** whitelisted. 
The proxy would allow outgoing calls to this domains: 

 - google.com
 - www.google.com
 - mail.google.com
 - api.google.com
 - google.de
 - www.google.de
 
This domains are blocked with the above configuration: 
 
 - mail.google.de
 - api.google.de

By starting the Docker container the file can be mounted into the running container. 

```
docker run -d -p 8888:8888 -v nginx_whitelist.conf:/usr/local/nginx/conf/nginx.conf reiz/nginx_proxy:latest 
```

Now the Docker container is running with the mounted configuration.

## Blacklist certain domains

This repository contains two nginx configuration files. 
The `nginx_blacklist.conf` file is built for the use case that you want to allow all outgoing traffic by default and only block traffic to some domains. 
In the first server section domains can be blacklisted by simply adding a 
`server_name *` line for each blacklisted domain. Here an example: 

```
    server {
        listen       8888;
        server_name  google.com;
        server_name  *.google.com;
        return 404;
    }
```

In the example above all pages would be accessible, but google.com and all subdomains of it would be blocked. Regex can be used here in the same way as in the whitelist example. 
By starting the Docker container the file can be mounted into the running container. 

```
docker run -d -p 8888:8888 -v nginx_whitelist.conf:/usr/local/nginx/conf/nginx.conf reiz/nginx_proxy:0.0.1 
```

Now the Docker container is running with the mounted configuration.

## Testing

You can test your configuration by pointing your Browser to the Nginx proxy in the running Docker container. 
If you run the Docker container on your localhost, then you can point your Browser to `localhost:8888`. 
Here is an example how it looks like in Firefox: 

![Firefox Proxy Settings](images/Firefox-Proxy-Settings.png)

## Configuring Docker and Kubernetes with a Proxy

Assuming you have a cluster of Docker machines (Kubernetes cluster)
and you would like to route all outgoing traffic to your proxy. 
That can be achieved by setting some global ENV variables on each Docker machine. 

For RedHat/CentOS version 6:

```shell
cat <<EOF | sudo tee -a /etc/sysconfig/docker
export http_proxy="http://myproxy.example.com:8888"
export https_proxy="https://myproxy.example.com:8888"
export no_proxy=<REGISTRY_IP>
EOF
 
sudo service docker restart
```

For RedHat/CentOS version 7, remove export:

```shell
cat <<EOF | sudo tee -a /etc/sysconfig/docker
http_proxy="http://myproxy.example.com:8888"
https_proxy="https://myproxy.example.com:8888"
no_proxy=<REGISTRY_IP>
EOF
 
sudo sed -i '/\[Service\]/a EnvironmentFile=/etc/sysconfig/docker' /usr/lib/systemd/system/docker.service
sudo systemctl daemon-reload
sudo service docker restart
```

For Ubuntu 14.04:

```shell
cat <<EOF | sudo tee -a /etc/default/docker
export http_proxy="http://myproxy.example.com:8888"
export https_proxy="https://myproxy.example.com:8888"
export no_proxy=<REGISTRY_IP>
EOF
 
sudo restart docker
```

For Kubernetes it works the same way. 
The `http_proxy` ENV has to be set before the K8S processes are starting.
Minikube can be started with proxy params directly.
Here an example: 

```shell
https_proxy=http://<PROXY_SERVER>:80 minikube start --docker-env HTTP_PROXY=http://<PROXY_SERVER>:80 --docker-env HTTPS_PROXY=http://<PROXY_SERVER>:80 --docker-env NO_PROXY=192.168.99.0/24
```

Alternatively the Proxy can be set by Container start as well: 

```shell
docker run -e "http_proxy=http://myproxy.example.com:8888" \
           -e "https_proxy=https://myproxy.example.com:8888" \
           -d liveperson\app run.sh
```

