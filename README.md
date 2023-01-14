# CI to publish on IPFS

This CI Action will CAR a directory, publish it on web3 storage, and update the DNS entry to point to the new CID


## Configuration

Configs happen by creating secret entries in the repo. 

- Select `Settings`
- Select `Secrets and Variables` on the left menu
- Select `Actions` on the sub menu
- Click `New Repository Secret`


`WEB3APITOKEN`: API Token created from web3storage


`HOSTNAME`:  
for `Digital Ocean`: Base domain  
for `Hurricane Electric`: full domain to be updated  

`HEPASSWORD`: Hurricane Electric Password

`DOTOKEN`: Digital Ocean personal token that can modify the domain

`DOID`: Digital Ocean unique id of the entry to be modified.  You can list the entries using
```
curl -X GET \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $DOTOKEN" \
  "https://api.digitalocean.com/v2/domains/$HOSTNAME/records"
```
