adaptto-website-xwalk-content
=============================

AEM site content for https://github.com/adaptto/adaptto-website-xwalk


Up- and Download Content from AEMaaCS author instance
-----------------------------------------------------

To up- and download content from the command line, you need an access token to authenticate against the AEM author instance. See documentation for details:
* https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/overview
* https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/local-development-access-token

To download content from AEM author instance:

```
mvn package -Dvault.unpack=true wcmio-content-package:download -Dsling.url=<author-url> -Dvault.oauth2AccessToken="<token>"
```

To upload content to AEM author instance:

```
mvn clean package wcmio-content-package:install -Dvault.bundleStatusURL="-" -Dsling.url=<author-url> -Dvault.oauth2AccessToken="<token>"
```

Replace `<author-url>` with the URL of your author instance, and `<token>` with a valid access token.