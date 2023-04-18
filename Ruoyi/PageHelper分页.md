*@Author fzm*
PageHelper&Mybatis实现分页
```java
startPage();
```
```java
/**  
* 设置请求分页数据  
*/  
public static void startPage()  
{  
	PageDomain pageDomain = TableSupport.buildPageRequest();  
	Integer pageNum = pageDomain.getPageNum();  
	Integer pageSize = pageDomain.getPageSize();  
	String orderBy = SqlUtil
		.escapeOrderBySql(pageDomain.getOrderBy());  
	Boolean reasonable = pageDomain.getReasonable();  
	PageHelper.startPage(pageNum, 
		pageSize, orderBy).setReasonable(reasonable);  
}
```

```java
/**  
* 封装分页对象  
*/  
public static PageDomain getPageDomain()  
{  
	PageDomain pageDomain = new PageDomain();  
	pageDomain.setPageNum(Convert
		.toInt(ServletUtils.getParameter(PAGE_NUM), 1));  
		
	pageDomain.setPageSize(Convert
		.toInt(ServletUtils.getParameter(PAGE_SIZE), 10));  
		
	pageDomain.setOrderByColumn(ServletUtils
		.getParameter(ORDER_BY_COLUMN));  
		
	pageDomain.setIsAsc(ServletUtils
		.getParameter(IS_ASC));  
		//reasonalble对参数进行逻辑处理，保证正确性
		//比如PageNum=0/-1时，PageNum=1
	pageDomain.setReasonable(ServletUtils
		.getParameterToBool(REASONABLE));  
		
	return pageDomain;  
}
```
-------
分页和查询的解耦
分页单独处理，查询该怎么写还怎么写
拦截器拦截语句

-----------
