
* https://community.sap.com/t5/financial-management-blogs-by-sap/sap-cpq-ironpython-clean-code-tips/ba-p/13495606
* https://help.sap.com/doc/5575a896ac9c49a7953328a19494bee6/2506/en-US/Help/html/1108d588-79c8-10e8-eb99-6e9d196af277.htm

### Available Scripting Battery

| Name                      | Type                                  |
|---------------------------|---------------------------------------|
| ApiResponseFactory        | Scripting.IApiResponseFactory         |
| Assert                    | Scripting.IAssert                     |
| AuthorizedRestClient      | Scripting.IAuthorizedRestClient       |
| BusinessPartnerRepository | Scripting.IBusinessPartnerRepository  |
| Convert                   | Scripting.IConvert                    |
| Cryptography              | Scripting.ICryptography               |
| F                         | Scripting.IAliases                    |
| FederationUtility         | Scripting.IFederationUtility          |
| FileHelper                | Scripting.IFileHelper                 |
| HttpUtility               | Scripting.IHttpUtility                |
| HttpWebClientProtocol     | Scripting.IHttpWebClientProtocol      |
| Items                     | Scripting.IRequestItems               |
| JsonHelper                | Scripting.IJsonHelper                 |
| JwtTokenProvider          | Scripting.Jwt.IJwtTokenProvider       |
| Log                       | Scripting.ILog                        |
| PartnerFunctionRepository | Scripting.IPartnerFunctionRepository  |
| Product                   | Scripting.IProduct                    |
| ProductHelper             | Scripting.IProductHelper              |
| QuoteHelper               | Scripting.Quote.IQuoteHelper          |
| RequestContext            | Scripting.IRequestContext             |
| RestClient                | Scripting.IRestClient                 |
| SalesArea                 | Scripting.ISalesArea                  |
| SamlAssertionProvider     | Scripting.ISamlAssertionProvider      |
| SapPassport               | Scripting.ISapPassport                |
| ScriptExecutor            | Scripting.IScriptExecutor             |
| Session                   | Scripting.ISession                    |
| SmtpClient                | Scripting.ISmtpClient                 |
| SoapHttpClientProtocol    | Scripting.ISoapHttpClientProtocol     |
| SqlHelper                 | Scripting.ISqlHelper                  |
| TagParserProduct          | Scripting.ITagParserProduct           |
| TagParserQuote            | Scripting.ITagParserQuote             |
| Trace                     | Scripting.ITrace                      |
| Translation               | Scripting.ITranslation                |
| User                      | Scripting.IUser                       |
| UserPersonalizationHelper | Scripting.IUserPersonalizationHelper  |
| WebServiceHelper          | Scripting.IWebServiceHelper           |
| WorkflowContext           | Scripting.IWorkflowContext            |
| XmlHelper                 | Scripting.IXmlHelper                  |
| mTLSRestClient            | Scripting.ImutualTLSRestClient        |

#### Get current Quote
```
context.Quote
```


#### Get Involved Parties
```
for i in QuoteHelper.Get('00020466').GetInvolvedParties():
    i.ExternalId = 'qwerty'
```

#### Update Items
```
for item in context.Items:
    Trace.Write('--Uplifting_Price--')
    item.Uplifting_Price.Value = item.ExtendedAmount.Value * 5
```


#### Get Items with Attibute Value
```
items = context.Quote.GetAllItems()
for item in items:
	Trace.Write("Item id: {0}".format(item.Id))
	for attr in item.SelectedAttributes:
		Trace.Write("Attribute name: {0}".format(attr.Name))
        for attrVal in attr.Values:
            Trace.Write("Value code: {0} Display: {1}".format(attrVal.ValueCode, attrVal.Display))
```

#### Variant Pricing Payload
```
for item in context.Quote.GetAllItems():
    current_pricing_json = item.VCItemPricingPayload

    for con in current_pricing_json.Conditions:
        #Trace.Write("Condition value {}: {}".format(con.ConditionType, float(con.ConditionRate)))

        if (con.ConditionType == "PPR0"):
            item.ListPrice = float(con.ConditionValue)
            #Trace.Write("set DiscountPercent:" + str(float(con.ConditionRate)))
```
