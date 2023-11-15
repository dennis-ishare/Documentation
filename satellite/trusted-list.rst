.. _refTrustedList:

Trusted list
============

Used to obtain the iSHARE trusted list of certificate authorities. Currently, eIDAS certificate issuer certificate authorities.


Parameters
~~~~~~~~~~

``Authorization``
    | **String (JWT)**.
    | OAuth 2.0 authorization based on bearer token. MUST contain “Bearer ” + access token value. How to retrieve the access token can be found at Access Token Endpoint section.


Response
--------

200
    | OK

::

    < Content-Type: application/json

 {
  "parties_token": {
    "iss": "EU.EORI.NL123456789",
    "sub": "EU.EORI.NL123456789",
    "aud": "EU.EORI.NL123456789",
    "jti": "378a47c4-2822-4ca5-a49a-7e5a1cc7ea59",
    "exp": 1504684475,
    "iat": 1504683475,
    "parties_info": {
      "count": 0,
      "data": [
        {
          "party_id": "EU.EORI.US000000005",
          "party_name": "Example Corporation",
          "capability_url": "https://www.example.com/capabilities",
          "registrar_id": "EU.EORI.NL123456789",
          "adherence": {
            "status": "Active",
            "start_date": "2023-01-31T00:00:00.000Z",
            "end_date": "2024-02-01T00:00:00.000Z"
          },
          "additional_info": {
            "description": "Example is a corporation providing example services to its customers in example regions",
            "logo": "https://www.example.com/logo.png",
            "website": "https://www.example.com/",
            "company_phone": "string",
            "company_email": "John.doe@example.com",
            "publicly_publishable": false,
            "countries_operation": [],
            "sector_industry": [],
            "tags": "mobility transport_operator"
          },
          "agreements": [
            {
              "type": "TermsOfUse",
              "title": "TOU",
              "status": "Accepted",
              "sign_date": "2023-01-31T00:00:00.000Z",
              "expiry_date": "2024-01-31T00:00:00.000Z",
              "hash_file": "614331b0003219f2d2d123b0cd6105fb",
              "framework": "iSHARE",
              "dataspace_id": "",
              "dataspace_title": "",
              "complaiancy_verified": "yes"
            },
            {
              "type": "AccessionAgreement",
              "title": "AA",
              "status": "Accepted",
              "sign_date": "2023-01-31T00:00:00.000Z",
              "expiry_date": "2024-01-31T00:00:00.000Z",
              "hash_file": "f50a036402b3b243910ce572930be9f5",
              "framework": "iSHARE",
              "dataspace_id": "",
              "dataspace_title": "",
              "complaiancy_verified": "yes"
            }
          ],
          "certificates": [
            {
              "subject_name": "SERIALNUMBER=EU.EORI.US000000005,CN=CFMInternational,O=CFM International,C=US",
              "certificate_type": "Pkio",
              "enabled_from": "2023-01-31T00:00:00.000Z",
              "x5c": "",
              "x5t#s256": ""
            }
          ],
          "spor": {
            "signed_request": "f1aec63b5b6f545718dc1c86efda3a9e8d8c74c4c2af42b39d9e8d41f3fc2b4e"
          },
          "roles": [
            {
              "role": "ServiceConsumer",
              "start_date": "2023-01-31T00:00:00.000Z",
              "end_date": "2024-01-31T00:00:00.000Z",
              "loa": "High",
              "compliancy_verified": true,
              "legal_adherence": true
            }
          ],
          "auth_registries": [
            {
              "name": "iSHARE Test Authorization Registry",
              "id": "EU.EORI.NL000000004",
              "url": "http://ar.isharetest.net/",
              "dataspace_id": "ContaktDS1",
              "dataspace_name": "ContaktDS1"
            }
          ]
        }
      ]
    }
  }
}

Extensions
~~~~~~~

``x-operation-settings``
    | **String**.
    | {"CollectParameters":false,"AllowDynamicQueryParameters":false,"AllowDynamicFormParameters":false,"IsMultiContentStreaming":false,"ErrorTemplates":{},"SkipAdditionalHeaders":false}

``x-unitTests``
    | **String**.
    |[{"request":{"method":"GET","uri":"/parties?active_only=true&name=ABC%20Corporation%0AABC%2A%0A%2ACorporation&eori=EU.EORI.NL123456789%0AEU.EORI.NL%2A%0A%2A123456789&certified_only=true&date_time=2023-01-31T00%3A00%3A00.000Z&adherenceStatus=%22Active%22%0A%22Revoked%22%0A%22Not%20Active%22%0A%22Pending%22&adherenceStartdate=2023-01-31T00%3A00%3A00.000Z&adherenceEnddate=2023-01-31T00%3A00%3A00.000Z&registarSatelliteID=EU.EORI.NL012345678&webSiteUrl=https%3A%2F%2Fwww.example.com&companyEmail=John.doe%40example.com&publiclyPublishable=true&tags=mobility&framework=iSHARE&subjectName=%22SERIALNUMBER%3DEU.EORI.US000000005%2CCN%3DCFMInternational%2CO%3DCFM%20International%2CC%3DUS%22&role=Service%20Consumer%0AService%20Provider%0AEntitled%20Party%0AAuthorisation%20Registry%0AIdentity%20Provider%0AIdentity%20Broker%0AiSHARE%20Satellite&loA=Low%0ASubstantial%0AHigh&compliancyVerified=true&legalAdherence=true&authorizationRegistryID=EU.EORI.NL000000004&authorizationRegistryName=%22Askme%20anything%22&dataSpaceID=EU.DSP.NLLOGISTICS_DLDS&dataSpaceTitle=%22Dutch%20Mobility%20Dataspace%22&countriesOfOperation=Belgium&sectorIndustry=Energy&page=2&certificate_subject_name=%22SERIALNUMBER%3DEU.EORI.US000000005%2CCN%3DCFMInternational%2CO%3DCFM%20International%2CC%3DUS%22"},"expectedResponse":{"x-allowExtraHeaders":true,"x-bodyMatchMode":"NONE","x-arrayOrderedMatching":false,"x-arrayCheckCount":false,"x-matchResponseSchema":true,"statusCode":"200","headers":{"Content-Type":"application/json"}},"x-testShouldPass":true,"x-testEnabled":true,"x-testName":"Test /parties","x-testDescription":"Search for participant information from your satellite. Various search parameters are supported as shown below. When results are more then 10 participants, pagination is used in response and each page contains up to 10 participants"}]
