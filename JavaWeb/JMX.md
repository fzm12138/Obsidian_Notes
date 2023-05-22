### Failed to retrieve application JMX service URL

configurations->disable JMX





@RunWith(SpringRunner.class)
@SpringBootTest(classes = ThreadPoolApplication.class)
public class HelloServiceTest {

    @Autowired
    HelloService helloService;

    @Test
    public void testSayHello() throws Exception {
        helloService.sayHello();
    }

