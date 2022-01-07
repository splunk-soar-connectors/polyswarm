[comment]: # "Auto-generated SOAR connector documentation"
# PolySwarm

Publisher: PolySwarm  
Connector Version: 1\.0\.3  
Product Vendor: PolySwarm  
Product Name: PolySwarm  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.2\.7532  

This app integrates with PolySwarm to implement investigate actions

[comment]: # " File: readme.md"
[comment]: # "  Copyright (c) PolySwarm, 2019."
[comment]: # "  "
[comment]: # "  Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
**PolySwarm:** Real-time threat intelligence from a crowdsourced network of security experts and
antivirus companies.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a PolySwarm asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | The Base URL to connect to
**polyswarm\_api\_key** |  required  | password | PolySwarm API Key
**polyswarm\_community** |  required  | string | PolySwarm Community

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using the supplied configuration  
[file reputation](#action-file-reputation) - Queries Polyswarm for file reputation info  
[url reputation](#action-url-reputation) - Queries Polyswarm for url reputation info  
[domain reputation](#action-domain-reputation) - Queries Polyswarm for Domain reputation info  
[ip reputation](#action-ip-reputation) - Queries Polyswarm for IP reputation info  
[get file](#action-get-file) - Downloads a file from Polyswarm and adds it to the vault  
[get report](#action-get-report) - Lookup results from UUID  
[detonate file](#action-detonate-file) - Upload a file to Polyswarm and retrieve analysis results  
[detonate url](#action-detonate-url) - Load a URL to Polyswarm and retrieve analysis results  

## action: 'test connectivity'
Validate the asset configuration for connectivity using the supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'file reputation'
Queries Polyswarm for file reputation info

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | File hash to query | string |  `hash`  `sha256`  `sha1`  `md5` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.hash | string |  `hash`  `sha256`  `sha1`  `md5` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'url reputation'
Queries Polyswarm for url reputation info

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to query | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'domain reputation'
Queries Polyswarm for Domain reputation info

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to query | string |  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.domain | string |  `domain` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'ip reputation'
Queries Polyswarm for IP reputation info

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to query | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get file'
Downloads a file from Polyswarm and adds it to the vault

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | File hash to download | string |  `hash`  `sha256`  `sha1`  `md5` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.hash | string |  `hash`  `sha256`  `sha1`  `md5` 
action\_result\.data\.\*\.vault\_id | string |  `vault id`  `sha1` 
action\_result\.summary\.vault\_id | string |  `vault id`  `sha1` 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get report'
Lookup results from UUID

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**scan\_uuid** |  required  | Lookup UUID | string |  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.scan\_uuid | string |  `uuid` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'detonate file'
Upload a file to Polyswarm and retrieve analysis results

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vault\_id** |  required  | Vault ID or SHA1 of the file to scan | string |  `sha1` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.vault\_id | string |  `sha1` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'detonate url'
Load a URL to Polyswarm and retrieve analysis results

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to query | string |  `url`  `domain`  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.url | string |  `url`  `domain`  `ip` 
action\_result\.data\.\*\.permalink | string | 
action\_result\.data\.\*\.positives | numeric | 
action\_result\.data\.\*\.scan\_uuid | string | 
action\_result\.data\.\*\.total | numeric | 
action\_result\.summary\.positives | numeric | 
action\_result\.summary\.scan\_uuid | numeric | 
action\_result\.summary\.total\_scans | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 