
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
