---
author: Alfresco Documentation
---

# Using an annotated controller

This example describes how to use Spring to write controllers to build the model that your page ultimately uses.

In this example, you want the page to display the hotels received from a query to a Hotels service. You do not want to just hard code it, but want to pull in content from a service that is an expert in all things hotel. A Spring developer would typically approach this by defining a new controller. With Spring 3.0, you can use annotated controllers to define a RESTful binding for the incoming request.

1.  Declare the annotated controller in its own Java bean. For example:

    ```
    @Controller
    public class HotelsController
    {
       privateTravelServicetravelService;
    
       @Autowired
       publicHotelsController(TravelServicetravelService) {
         this.travelService = travelService;
       }
    
       @RequestMapping("/hotels")
       public void getHotels(SearchCriteria criteria, Model model) {
          List<Hotel> hotels = travelService.findHotels(criteria);
          model.addAttribute(“hotelList”, hotels);
       }
    }
    ```

    This Java bean is annotated to inform Spring to bind to the incoming URL of /hotels. When the Spring MVC dispatcher servlet must identify the controller that can handle the incoming URL, it consults these annotations to find your bean. As you can see by the code, all the “heavy lifting” is done inside the bean. It calls out to the travelService to retrieve a list of hotel properties, places these into the model, and then returns it. In this example, you are populating the model in the controller. So far, this is all Spring Web MVC.

2.  Adjust your Surf template to use this model data. For example:

    ```
    <html>
       <body>
          <table>
          <#if hotelList?size == 0>
             <tr>
                <td colspan="2">No hotels found</td>
             </tr>
          <#else>
             <#list hotelList as hotel>
             <tr>
                <td>${hotel.name}</td>
                <td>${hotel.address}</td>
             </tr>
             </#list>
          </#if>
          </table>
       </body>
    </html>
    ```


You used Spring Web MVC to define your controller. The model generated by the controller is available to your Surf template. You mapped your controller and page to the same `/hotels` URI and let the framework figure stuff out for you.

**Parent topic:**[Spring Web MVC](../concepts/spring-web-mvc.md)
