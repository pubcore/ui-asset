# Supports developer synchronizing asset-keys used in source-code and default asset.json file
Map asset keys to asset uris, returns asset uri..


# Configuration
```
import {initEnvIsDev, initDefaults, initAutoupdateDefaults} from '@pubcore/ui-asset'

//initial asset.json content is a empty json object {}
import defaultAsset from '../asset.json'

//if isDev is true then system will throw exceptions on wrong default data
initEnvIsDev(isDev)

// enables asset-key sync feature
initDefaults(defaultAsset)

// postUri points on a service which will write asset-key with asset uris to asset.json file
initAutoupdateDefaults({
	postUri:'/service/asset
})
```

## Examples
```
import uiAsset from '@pubcore/ui-asset'
var A = {
	logo:uiAsset(A,'logo','/image/logo.png'})
	keyvisual:uiAsset(A,'keyvisual','/image/keyvisual.png'})
}

//Will log /img/logo.png and if postUri service exists on dev will also write
//a default {logo:{uri:'/image/l.png'}} into asset.json file
console.log(
	uiAsset(
		A,
		'logo',
		{logo:{uri:'/image/l.png'} //default which will be written in asset.json file, only on dev system
	)
)
```
