CloudFlareDynDns
--------------
Updates specified CloudFlare DNS hostname to the current connection's external IP address using CloudFlare API v4 https://api.cloudflare.com/
		
This module is useful for homelabs. Remember how DynDns used to dynamically update your IP address for free? The functionality provided by this module is similar but updates CloudFlare hosted domains. CloudFlare is free and awesome, and I recommend it, if even for its simplified DNS management and free HTTPS.
		
This should be setup as a scheduled task. I set mine for 5 minutes.

### Install
	mkdir "$($Env:PSModulePath -split ';' | Select-Object -first 2 | Select-Object -Last 1)\CloudFlareDynDns"
	wget "https://raw.githubusercontent.com/caothu159/modules/master/CloudFlareDynDns/CloudFlareDynDns.psm1" -UseBasicParsing -OutFile "$($Env:PSModulePath -split ';' | Select-Object -first 2 | Select-Object -Last 1)\CloudFlareDynDns\CloudFlareDynDns.psm1"

Examples
-----
	Update-CloudFlareDynamicDns -Token 1234567893feefc5f0q5000bfo0c38d90bbeb -Email example@example.com -Zone example.com -Record homelab
	Update-CloudFlareDynamicDns -Token 1234567893feefc5f0q5000bfo0c38d90bbeb -Email example@example.com -Zone example.com -Record homelab -UseDns
