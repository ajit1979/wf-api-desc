Create a new workflow endpoint:
https://workflow-staging.signavio.com/api/v1/5a27c5b6d9383b14da6c9619/workflows

Example Curl:

```bash
curl 'https://workflow-staging.signavio.com/api/v1/5a27c5b6d9383b14da6c9619/workflows' \
  -H 'accept: */*' \
  -H 'accept-language: en-US,en;q=0.9,de;q=0.8,hi;q=0.7,zh-CN;q=0.6,zh;q=0.5,cy;q=0.4,fr;q=0.3' \
  -H 'authorization: undefined' \
  -H 'content-type: text/plain;charset=UTF-8' \
  -b 'notice_preferences=1:; notice_gdpr_prefs=0,1:; cmapi_gtm_bl=ta-asp-bzi-sp-awct-cts-csm-img-flc-fls-mpm-mpr-m6d-tc-tdc; cmapi_cookie_privacy=permit 1,2 functional; optout_domains={"Required Cookies":{"domains":{"signavio.com":"1","editor.signavio.com":"1","workflow.signavio.com":"1","prod-assets.signavio.com":"1","consent.trustarc.com":"1"},"value":"0"},"Functional Cookies":{"domains":{"cdn.eu.pendo.io":"1","*.siteintercept.qualtrics.com":"1","siteintercept.qualtrics.com":"1"},"value":"1"}}; _ga=GA1.1.2119776966.1745395437; AMCV_227AC2D754DCAB340A4C98C6%40AdobeOrg=179643557%7CMCMID%7C43460854680787547170969832603301909930%7CMCAID%7CNONE%7CvVersion%7C5.5.0; _pendo___sg__.a31c9b05-696d-4d52-7030-ba294c45ff51=%7B%22visitormetadata%22%3A%7B%22agent__country%22%3A%22Germany%22%2C%22agent__isadmin%22%3Atrue%2C%22agent__language%22%3A%22en_US%22%7D%2C%22accountmetadata%22%3A%7B%22agent__licenses%22%3A%22%5B%5C%22Enterprise%20Plus%20Edition%5C%22%5D%22%2C%22agent__featurepackages%22%3A%22%5B%5C%22hubNextBetaOptIn%5C%22%2C%5C%22hubNext%5C%22%2C%5C%22portalInteractiveBdm%5C%22%2C%5C%22a2017_enterprise_plus%5C%22%2C%5C%22order%5C%22%5D%22%2C%22agent__groups%22%3A%22%5B%5C%22Administrators%5C%22%5D%22%2C%22agent__tenantname%22%3A%22Signavio%20(PM%20Integration)%22%7D%7D; hubspotutk=ad608b3b3bad673fded5e8f2ad723cb7; _pendo_utm.a31c9b05-696d-4d52-7030-ba294c45ff51=%7B%22referrer%22%3A%22staging.signavio.com%22%7D; rxVisitor=1733473698796FD3B5GNMVVIEMNGUHA8HRS0AKEOPNEMP; _pendo_unsentEvents.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_visitorId.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_visitorId.3566341439=_PENDO_T_tORXbw2abhw; _pendo_accountId.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_sessionId.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_meta.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_oldVisitorId.b8b3804b-5f4e-4153-607e-73acfce08054=; notice_behavior=implied,eu; _pendo_unsentEvents.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_visitorId.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_accountId.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_meta.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_oldVisitorId.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_sessionId.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=; _pendo_utm.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=%7B%22referrer%22%3A%22workflow-staging.signavio.com%22%7D; _pendo___sg__.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=%7B%22visitormetadata%22%3A%7B%22agent__country%22%3A%22%22%2C%22agent__isadmin%22%3Afalse%2C%22agent__language%22%3A%22en_US%22%7D%2C%22accountmetadata%22%3A%7B%22agent__licenses%22%3A%22%5B%5D%22%2C%22agent__featurepackages%22%3A%22%5B%5D%22%2C%22agent__groups%22%3A%22%5B%5D%22%2C%22agent__tenantname%22%3A%22%22%7D%7D; s_plt=1.01; s_pltp=undefined; at_check=true; mbox=session#6dbdc3d7b6f24e29824c0f5272df7d82#1758201304|PC#6dbdc3d7b6f24e29824c0f5272df7d82.37_0#1821444244; notice_behavior=implied,eu; s_cc=true; __hstc=117173593.ad608b3b3bad673fded5e8f2ad723cb7.1752049022197.1752049022197.1758199444261.2; __hssrc=1; _ga_L9S3ZB2BF6=GS2.1.s1758199443$o6$g0$t1758199445$j58$l0$h255964546; dtCookie=v_4_srv_35_sn_8F117C1AEECB6D898251DFCD5871DEB3_perc_100000_ol_0_mul_1_app-3A128f57526be53d68_1_app-3Aea7c4b59f27d43eb_1_app-3Abe2f5e773405d766_1_app-3Afb27f1103e7d0935_1_app-3A168807ded34e0b37_1_app-3A9f184dac65f42ff9_1_app-3Ae60d30ddf31be2fb_1_app-3A0ebe49c47d203a08_1; _pendo___sg__.b8b3804b-5f4e-4153-607e-73acfce08054=%7B%22visitormetadata%22%3A%7B%22agent__country%22%3A%22Germany%22%2C%22agent__isadmin%22%3Atrue%2C%22agent__language%22%3A%22en_US%22%7D%2C%22accountmetadata%22%3A%7B%22agent__licenses%22%3A%22%5B%5C%22Enterprise%20Plus%20Edition%5C%22%2C%5C%22Workflow%5C%22%5D%22%2C%22agent__featurepackages%22%3A%22%5B%5C%22hubNextBetaOptIn%5C%22%2C%5C%22hubNext%5C%22%2C%5C%22a2017_workflow%5C%22%2C%5C%22portalInteractiveBdm%5C%22%2C%5C%22a2017_enterprise_plus%5C%22%2C%5C%22order%5C%22%5D%22%2C%22agent__groups%22%3A%22%5B%5C%22Administrators%5C%22%5D%22%2C%22agent__tenantname%22%3A%22Signavio%20(PM%20Integration)%22%7D%7D; _pendo_guides_blocked.b8b3804b-5f4e-4153-607e-73acfce08054=0; _pendo_utm.b8b3804b-5f4e-4153-607e-73acfce08054=; _pendo_utm.3566341439=%7B%22referrer%22%3A%22staging.signavio.com%22%7D; statereference=WfZUzg0apH9FMuCIFmzGJP2PgHNhDD3Ag4OT; workflow-authentication=e1zJPleyyenlb57JeLAymWystw08oQF9TmuM; spg-csrf-token="QNBge0Hkbl9gHHpPf9eo71oxGLo4s6b0Nqlf5Sjr6KY="; TAsessionID=1551dac4-5a50-4a53-acc6-f4b92a2ba60d|EXISTING; _pendo_accountId.3566341439=5a27c5b6d9383b14da6c961a; _pendo_guides_blocked.c9aba383-6ca4-4cfd-40ec-47bce5e8e93d=0; _pendo_meta.3566341439=2963462528; dtSa=false%7CC%7C44%7CdTMasked_DIV%7Cfetch%7C1759309232869%7C109122425_280%7Chttps%3A%2F%2Fworkflow-staging.signavio.com%2F5a27c5b6d9383b14da6c9619%2Fprocesses%2Foverview%7C%7C%7C%7C; _pendo_sessionId.3566341439=%7B%22sessionId%22%3A%22QJNyxZqPc5krFsAC%22%2C%22timestamp%22%3A1759309237553%7D; rxvt=1759311040621|1759308393327; dtPC=35$108474255_233h99p35$109122425_280h55vVLKKRHASMGLIUIDRASIFDLJEUUSPPAUG-0e0' \
  -H 'origin: https://workflow-staging.signavio.com' \
  -H 'priority: u=1, i' \
  -H 'referer: https://workflow-staging.signavio.com/5a27c5b6d9383b14da6c9619/processes/create' \
  -H 'sec-ch-ua: "Chromium";v="140", "Not=A?Brand";v="24", "Google Chrome";v="140"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "macOS"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/140.0.0.0 Safari/537.36' \
  -H 'x-csrf-token: QNBge0Hkbl9gHHpPf9eo71oxGLo4s6b0Nqlf5Sjr6KY=' \
  -H 'x-dtpc: 35$109122425_280h55vVLKKRHASMGLIUIDRASIFDLJEUUSPPAUG-0e0' \
  --data-raw '{"id":"t3g3p4ce0tcpnrebn8","name":"abc","trigger":null,"activities":[],"transitions":[],"variables":[],"labelIds":[],"diagram":{"canvas":{"children":[],"bounds":{"upperLeft":{"x":0,"y":0},"lowerRight":{"x":0,"y":0}}},"edges":[]},"coreInformation":{"fields":[]}}'
```

Example Response:
{
    "name": "abc",
    "activities": [],
    "transitions": [],
    "variables": [],
    "id": "68dcedb8843ee973933be5fc",
    "organizationId": "5a27c5b6d9383b14da6c961a",
    "involvedUserIds": [],
    "involvedGroupIds": [],
    "lastUpdated": "2025-10-01T09:00:40.971Z",
    "enableCases": false,
    "diagram": {
        "canvas": {
            "bounds": {
                "lowerRight": {
                    "x": 0.0,
                    "y": 0.0
                },
                "upperLeft": {
                    "x": 0.0,
                    "y": 0.0
                }
            },
            "children": []
        },
        "edges": [],
        "version": 1
    },
    "coreInformation": {
        "fields": []
    },
    "changed": true,
    "editorId": "66ea8df96483b76785e90b2e",
    "editorLock": "2025-10-01T09:00:40.971Z",
    "ownerId": "66ea8df96483b76785e90b2e",
    "labelIds": [],
    "editor": {
        "id": "66ea8df96483b76785e90b2e",
        "color": "#83cb76",
        "firstName": "Ajit Singh",
        "groupIds": [],
        "lastName": "Chahal",
        "emailAddress": "ajit.singh.chahal@sap.com",
        "organizationIds": []
    },
    "owner": {
        "id": "66ea8df96483b76785e90b2e",
        "color": "#83cb76",
        "firstName": "Ajit Singh",
        "groupIds": [],
        "lastName": "Chahal",
        "emailAddress": "ajit.singh.chahal@sap.com",
        "organizationIds": []
    },
    "labels": [],
    "published": false
}
