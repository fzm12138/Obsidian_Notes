- Declare the strategy of how to generator primary key
	- At Default situation JPA choose one most-suitable database's primary key strategy automicly which is:
		- **SqlServer correspond identity
		- **Mysql correspond increment**
### javax.persisitence.GenerationType defined these strategies:
- IDENTITY : ID auto-increasement  (Oracle doesn't support it)
- AUTO : JPA choose suitable strategy automicly (default option)
- SEQUENCE : Using sequence produce PK, via @SequenceGeneratoor assgins sequence name,mysql doesn't support it
- TABLE : via table generator PK , framwork using table simulate generator PK,using this strategy making application easier transplant DB