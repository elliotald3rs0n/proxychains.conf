# proxychains.conf  VER 4
#
#        HTTP, SOCKS4, SOCKS5 tunneling proxifier with DNS.
#	

# The option below identifies how the ProxyList is treated.
# only one option should be uncommented at time,
# otherwise the last appearing option will be accepted
#
#dynamic_chain
#
# Dynamic - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# at least one proxy must be online to play in chain
# (dead proxies are skipped)
# otherwise EINTR is returned to the app
#
strict_chain
#
# Strict - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# all proxies must be online to play in chain
# otherwise EINTR is returned to the app
#
#random_chain
#
# Random - Each connection will be done via random proxy
# (or proxy chain, see  chain_len) from the list.
# this option is good to test your IDS :)

# Make sense only if random_chain
#chain_len = 2

# Quiet mode (no output from library)
#quiet_mode

# Proxy DNS requests - no leak for DNS data
proxy_dns 

# set the class A subnet number to usefor use of the internal remote DNS mapping
# we use the reserved 224.x.x.x range by default,
# if the proxified app does a DNS request, we will return an IP from that range.
# on further accesses to this ip we will send the saved DNS name to the proxy.
# in case some control-freak app checks the returned ip, and denies to 
# connect, you can use another subnet, e.g. 10.x.x.x or 127.x.x.x.
# of course you should make sure that the proxified app does not need
# *real* access to this subnet. 
# i.e. dont use the same subnet then in the localnet section
#remote_dns_subnet 127 
#remote_dns_subnet 10
remote_dns_subnet 224

# Some timeouts in milliseconds
tcp_read_time_out 15000
tcp_connect_time_out 8000

# By default enable localnet for loopback address ranges
# RFC5735 Loopback address range
localnet 127.0.0.0/255.0.0.0
# RFC1918 Private Address Ranges
# localnet 10.0.0.0/255.0.0.0
# localnet 172.16.0.0/255.240.0.0
# localnet 192.168.0.0/255.255.0.0


# Example for localnet exclusion
## Exclude connections to 192.168.1.0/24 with port 80
# localnet 192.168.1.0:80/255.255.255.0

## Exclude connections to 192.168.100.0/24
# localnet 192.168.100.0/255.255.255.0

## Exclude connections to ANYwhere with port 80
# localnet 0.0.0.0:80/0.0.0.0

# ProxyList format
#       type  host  port [user pass]
#       (values separated by 'tab' or 'blank')
#
#
#        Examples:
#
#            	socks5	192.168.67.78	1080	lamer	secret
#		http	192.168.89.3	8080	justu	hidden
#	 	socks4	192.168.1.49	1080
#	        http	192.168.39.93	8080	
#		
#
#       proxy types: http, socks4, socks5
#        ( auth types supported: "basic"-http  "user/pass"-socks )
#
[ProxyList]
# add proxy here ...
# meanwile
# defaults set to "tor"
http  13.56.2.56 8090
http  134.209.61.152 8080
http  134.209.1.204 3128
http  134.209.13.25 3128
http  134.209.52.246 3128
http  134.209.1.204 8080
http  104.152.45.45 80
http  104.248.51.47 8080
http  104.152.45.46 80
http  134.209.166.42 8080
http  104.248.66.103 3128
http  134.209.195.94 8080
http  104.236.248.219 3128
http  12.187.254.101 8080
http  134.209.26.78 8080
http  134.0.63.134 8000
socks4  198.1.120.123 6774
http  132.148.148.221 80
http  104.248.156.229 8080
http  104.245.228.65 8080
http  103.35.64.12 3128
http  104.236.54.196 8080
http  103.122.104.133 8080
http  103.31.45.174 8080
http  103.28.227.69 3128
http  102.68.129.6 8080
http  104.248.115.236 80
http  103.224.36.49 81
http  103.206.132.180 8060
http  103.226.51.80 8080
http  103.209.89.66 8080
http  103.124.236.250 8080
http  103.250.157.43 6666
http  103.127.171.52 3128
http  103.205.59.38 8080
http  103.25.195.2 80
http  104.236.51.165 8080
http  108.61.222.139 8118
http  134.209.40.237 3128
http  1.1.174.58 8080
http  103.12.20.6 9000
http  103.224.38.2 81
http  103.254.59.50 8080
http  134.209.199.35 3128
http  103.121.42.229 8080
http  134.209.199.184 3128
http  103.216.232.111 8080
http  1.179.185.253 8080
http  1.20.103.171 8080
http  134.209.196.104 3128
http  101.109.59.254 8080
http  1.4.203.86 8080
http  101.109.113.168 3128
http  101.109.139.159 8080
http  102.182.119.53 8080
socks5  207.97.174.134 1080
http  134.209.199.138 3128
http  104.248.144.223 8080
http  1.175.131.197 3128
http  1.179.183.109 8080
http  103.105.195.233 8080
http  114.199.123.194 8080
http  101.255.121.41 8080
http  101.108.243.88 8080
http  103.204.209.202 8080
socks5  35.236.180.213 1080
http  103.101.233.13 8080
socks5  104.238.97.230 7850
http  101.109.221.253 8080
http  103.127.171.52 8080
socks4  157.230.101.76 1080
http  47.52.65.231 3128
http  103.112.63.121 8080
socks5  35.221.170.161 8081
http  101.109.106.100 8080
http  103.119.145.38 80
http  103.106.3.97 8080
http  1.0.139.171 8080
http  103.105.77.38 8181
http  12.189.125.134 8080
http  103.119.54.48 8080
http  103.194.233.89 8080
http  1.2.188.172 8080
http  103.18.134.38 80
http  1.20.217.221 8080
socks4  104.238.97.129 1074
http  103.105.77.23 8181
http  103.111.56.41 8080
http  217.79.3.94 8080
http  103.25.47.130 8080
http  134.209.16.40 3128
http  1.179.185.249 8080
http  101.108.27.161 8080
http  13.58.154.61 80
http  103.17.37.85 8080
http  1.179.183.89 8080
http  103.114.10.145 8080
http  103.109.3.228 8080
http  103.102.12.161 8082
socks5  18.223.124.243 3130
http  103.197.92.174 8080
http  103.46.209.74 8080
http  103.129.152.142 80
http  103.133.223.119 8080
http  104.155.103.87 80
http  103.122.66.159 8080
http  103.196.233.167 8080
http  1.20.102.54 8080
http  103.122.104.132 8080
http  103.124.144.154 80
http  103.104.58.13 8080
http  134.209.36.236 8080
http  161.49.186.218 8080
http  103.114.10.246 8080
http  103.29.90.134 8080
http  103.114.21.18 8080
http  103.248.30.42 8080
http  64.20.33.202 8080
http  103.30.115.162 80
http  102.141.169.46 8080
http  134.209.199.69 3128
http  103.12.20.113 9000
http  104.248.117.3 8080
