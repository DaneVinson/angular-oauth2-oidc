# angular-oauth2-oidc For Azure Active Directory B2C

This repository is a fork of the [angular-oauth2-oidc](https://github.com/manfredsteyer/angular-oauth2-oidc) project modified to work with Azure Active Directory B2C. 

## Setup
Sample setup for the OAuthService in an application's root compenent constructor is as follows:

    constructor(private oAuthService: OAuthService) {
	    this.oAuthService.aadb2c = true;
	    this.oAuthService.clientId = '{AAD_B2C_App_Id}';
	    this.oAuthService.loginUrl = 'https://login.microsoftonline.com/{AAD_B2C_Tenant}.onmicrosoft.com/oauth2/v2.0/authorize'
	    this.oAuthService.logoutRedirectUri = window.location.origin + '/about';
	    this.oAuthService.logoutUrl = 'https://login.microsoftonline.com/{AAD_B2C_Tenant}.onmicrosoft.com/oauth2/v2.0/logout';        
	    this.oAuthService.oidc = true;
	    this.oAuthService.redirectUri = window.location.origin + '/dashboard';  // login redirect
	    this.oAuthService.scope = 'openid profile';
	    this.oAuthService.aadb2cPolicy = '{AAD_B2C_Policy}';
    }

- AAD_B2C_App_Id - The unique Application Id for the Azure Active Directory application
- AAD_B2C_Tentant - The Azure Active Directory tentant name
- AAD_B2C_Polity - The Azure Active Directiory B2C Policy Id to use, e.g. b2c_1_signuporsigninpolicy

Please see the original angular-oauth2-oidc project for further setup and usage details.