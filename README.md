**Create Viseeon Cash Instance**
----
  _Create a new viseeon cash instance._

* **URL**

  `{{api}}`/instances

* **Method**
  
  `POST` 
  
*  **Body Payload**

```json
{
			"instanceId": "[string]",

			"instanceCurrencyId": "[string]",

			"instanceCompany": "[string]",

			"instanceUserName": "[string]",

			"instanceUserEmail": "[string]",

			"partnerDomain": "[string]",

			"useAliasOnDuplication": [boolean]
}
```
   **instanceId** `[required][length=min:2-max:15][no-whitespace][no-special-character] [i.e. company]`
   
   **instanceCurrencyId** `[required][length=max:15] [i.e. EUR]`
   
   **instanceCompany** `[required][length=max:40] [i.e. Company, Inc]`
   
   **instanceUserName** `[required][length=max:100] [i.e. Jonh Doe]`
   
   **instanceUserEmail** `[required][valid-email-structure][length=max:90] [i.e. jonh.doe@example.com]`
   
   **partnerDomain** `[i.e. viseeon.cash]`
   
   **useAliasOnDuplication** `[i.e. true]`
   

   * **Body Notes**
 
	   * _Use always value `viseeon.cash` for the `partnerDomain` property, the new instance will be accessible at https://`instanceId`.viseeon.cash_
	   * _Set `true` for `useAliasOnDuplication` property, the API will create the instance with an alternate ID if the provided `instanceId` already exist._
  

* **Success Response**
  
  _The API will return HTTP 201 (CREATED) code on a new instance._

  * **Http Code:** 201 <br />

**HTTP Headers**

  _All Headers are required_

  **APPLICATION-ID**
  
  **TENANT-ID**

 * **Headers Notes**
	* _Use always value  `instancecreator`  for the  `TENANT-ID`  header (the value `instancecreator` tell the API to allow instance creation)._
	* _The value of `APPLICATION-ID` will be provided (The techincal partner will provide the application id)._




**Example :**

  _The example below show viseeon cash instance creation with company **ABCDEFG, Lda** and user **Jonh Doe (jonh.doe@example.com)**_

`BODY`
```json
{
			"instanceId": "abcdefglda",

			"instanceCurrencyId": "EUR",

			"instanceCompany": "ABCDEFG, Lda",

			"instanceUserName": "Jonh Doe",

			"instanceUserEmail": "jonh.doe@example.com",

			"partnerDomain": "viseeon.cash",

			"useAliasOnDuplication": true
}
```
`HEADERS`

`APPLICATION-ID:` 123456789

`TENANT-ID:` instancecreator
