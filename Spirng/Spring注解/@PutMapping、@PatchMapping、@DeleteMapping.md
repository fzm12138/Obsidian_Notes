## PutMapping
- 从user向server发送data，**与post不同的是put的真正目的是进行大规模替换操作，而不是更新操作**
- put意味着将*数据放到这个url上*，本质就是替换已有的数据
- 若省略了某个属性，那么该属性的值就会被null替代
--------
## patchMapping
- 对资源数据打补丁或者进行局部更新
*eg:*
```java
@PatchMapping(path="/{orderId}",consumes="application/json")
public Order patchOrder(@PathVariable("orderId") Long orderId, 
						@RequestBody Order patch){
    Order order = repo.findById(orderId).get();
    if(patch.getDeliveryName()!=null){
        order.setDeliveryName(patch.getDeliveryName());
    }
    ......   //下列都是类似的代码
    return repo.save(order);
}
```
- 允许只有修改的内容非null时，才在本地数据库的对应属性上修改
- 若user没改动，则属性不动，也就是对资源数据进行一个局部属性的更新，不对整个实体进行更新
- 在**GetMapping**和**PatchMapping**中，引用的路径请求都是要变更的资源
--------
## DeleteMapping
- user可以通过**HTTP DELETE**请求来移除某个资源
*eg:*
```java
@DeleteMapping("/{orderId}")
@ResponseStatus(code=HttpStatus.NO_CONTENT)
public void deleteOrder(@PathVariable("orderId") Long orderId){
    try{
        repo.deleteById(orderId);
    }catch(EmptyResultDataAccessException e){}
}
```
- 在这个方法中，真正负责删除订单的是里面的代码，**@DeleteMapping**指定 *deleteOrder()*** 方法处理针对“/orders/{orderId}的**DELETE**请求。
- 注意：**@ResponseStatus**注解保证HTTP状态码为**204**
	- 已经不存在的资源没必要返回任何资源数据给user
	- 因此delete请求中通常没有响应体，要以HHTP状态码的形式让user知道不要期望获得任何内容