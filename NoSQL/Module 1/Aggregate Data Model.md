A data model is the model through which we perceive or manipulate data. 

Relational model takes the information that we want to store and divides it into tuples and relations. A tuple is a limited data structure and doesn't support complex structures like nested tuples. 

Aggregate orientation takes a different approach. It assumes that the data you are operating on is much more complex than a simple tuple. Key value, document and column-family databases all use this more complex records. Dealing with aggregates makes it much more easier for databases that operate on clusters as aggregates makes a natural unit for sharding and replication. Aggregates are also much more easier to deal with for application programmers as they usually deal with data similar to aggregate structures. 

![[Pasted image 20241021021013.png]]

![[Pasted image 20241021021211.png]]

![[Pasted image 20241021021242.png]]

Customer representation in NoSQL
```
{ "id":1, "name":"Martin", "billingAddress":[{"city":"Chicago"}] }
```

Order representation in NoSQL
```
{ "id":99, "customerId":1, 
"orderItems": [ 
	{ "productId":27, "price": 32.45, "productName": "NoSQL Distilled" } 
	], 
"shippingAddress":[{"city":"Chicago"}], 
"orderPayment":[ 
		{ 
			"ccinfo":"1000-1000-1000-1000", "txnId":"abelif879rft",
			"billingAddress": {"city": "Chicago"} 
		} 
	], 
}
```

In this model, we have two main aggregates: customer and order. We’ve used the blackdiamond composition marker in UML to show how data fits into the aggregation structure. The customer contains a list of billing addresses; the order contains a list of order items, a shipping address, and payments. The payment itself contains a billing address for that payment. 

A single logical address record appears three times in the example data, but instead of using IDs it’s treated as a value and copied each time. This fits the domain where we would not want the shipping address, nor the payment’s billing address, to change. In a relational database, we would ensure that the address rows aren’t updated for this case, making a new row instead. With aggregates, we can copy the whole address structure into the aggregate as we need to.
