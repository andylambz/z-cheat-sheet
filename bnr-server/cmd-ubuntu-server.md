# CMD UBUNTU SERVER

## View Internal IP
hostname -I

## View Public IP
curl ifconfig.me

## Telnet
nc -vz <ip-address> 8892
nc -zv 43.199.112.106 22000

***

# Firewall

#@ Allow port
sudo ufw allow 8893/tcp

## Check port listen
sudo lsof -i :8893

## Check port listen
sudo ss -tulnp | grep 8892

# Check outbound gitlab from server
ssh -T git@gl.owvn.org
