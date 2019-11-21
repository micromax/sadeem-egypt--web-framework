<h1 id="template">Sadeem web framework&nbsp;</h1>
<p>vertx based web&nbsp;framework</p>
<p>https://github.com/micromax/sadeem-egypt--web-framework</p>
<p>http://sadeem-egypt.com</p>
<h2 id="">An java web framework by sadeem-egypt.com , lightweight, builtin server, from developer to developers.</h2>
<p>gradle project so you will be happy with it</p>
<p>small footprint support Java&nbsp; Kotlin and scala .</p>
<p>MVC pattern&nbsp;</p>
<p>very strong built-in web server i could handle 35k&nbsp;request per second based on&nbsp;vertx.io&nbsp;</p>
<p>databse driver for MYsql is included</p>
<p>ORM and database <span style="text-decoration: underline;"><strong>migration</strong></span>&nbsp;included thanks to Ebean ORM , you could also use your own ORM .</p>
<p>akka java actor famework&nbsp;included</p>
<p>Non blocking :-)&nbsp;</p>
<p>&nbsp;</p>
<p>you find example for Controller and Models and view&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<h2 id="alittlehistory">Recommended documentation</h2>
<p>you could start build Web app , realtime app and IoT GetWay's or even blockchan , without reading and doc's for based&nbsp;technologys&nbsp;</p>
<p>1 -&nbsp;<a href="https://vertx.io/">https://vertx.io/</a>&nbsp;</p>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Eclipse Vert.x is a tool-kit for building reactive applications on the JVM</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>2 -&nbsp;<a href="https://akka.io/">https://akka.io/</a>&nbsp;</p>
<p>Akka, a set of open-source libraries for designing scalable, resilient systems that span processor cores and networks. Akka allows you to focus on meeting business needs instead of writing low-level code to provide reliable behavior, fault tolerance, and high performance.</p>
<p>Many common practices and accepted programming models do not address important challenges inherent in designing systems for modern computer architectures. To be successful, distributed systems must cope in an environment where components crash without responding, messages get lost without a trace on the wire, and network latency fluctuates. These problems occur regularly in carefully managed intra-datacenter environments - even more so in virtualized architectures.</p>
<p>&nbsp;</p>
<p>3 -&nbsp;<a href="https://ebean.io/">https://ebean.io/</a></p>
<p>&nbsp;</p>
<p>&nbsp; &nbsp; ORM&nbsp;</p>
<p>&nbsp;Ebean provides a simple programming model that developers can understand and master quickly.</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>4 -&nbsp;<a href="https://freemarker.apache.org/">https://freemarker.apache.org/</a></p>
<p>&nbsp;</p>
<p>Apache FreeMarker&trade; is a&nbsp;<em>template engine</em>: a Java library to generate text output (HTML web pages, e-mails, configuration files, source code, etc.) based on templates and changing data. Templates are written in the FreeMarker Template Language (FTL), which is a simple, specialized language (not a full-blown programming language like PHP). Usually, a general-purpose programming language (like Java) is used to prepare the data (issue database queries, do business calculations). Then, Apache FreeMarker displays that prepared data using templates. In the template you are focusing on how to present the data, and outside the template you are focusing on what data to present.</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Get Start&nbsp;</strong></p>
<p>&nbsp;</p>
<p><strong>will clone &amp; open Examples&nbsp;</strong></p>




<p> 1 - import  Gradle Project to your IDE </p>

PS it may take time and if you need Scala you have to install it to your machine and 
enable it as plugin in Gradle file by uncomment it 

<p><strong> Config Files   </strong></p>

<p>
    <strong> <li> application.properties </li> </strong>
    <strong> <li> database.properties </li> </strong>
    <strong> <li> route.properties </li> </strong>
        
    
    
</p>
<p>application.properties</p>
<p>
    this file hold main config for Host and Port
    Ebean(ORM) conf ... etc 
    change port for what you want 9999 for example 
    
    run Gradle task Build from IDEA or command Line
    thank hit run task 
    or Run boot.java (this main class )
    
    
</p>


<p>

you are ready now go to 
<code>http://localhost:8977/Hellojava </code> 

if it's work than can go also to Kotlin example
<code>http://localhost:8977/HelloKotlin </code> 



</p>

if every thing is Ok now you need  a real life example 

<p><strong>CRUD example</strong></p>


create database i use Mysql user your own or even use H2 bout don't forget to add 
your driver in Gradle file



<p><strong> Make your database Config correct  at this files</strong></p>


<li>/resources/application.properties</li>
<li>/resources/application.yaml</li>
<li>/resources/database.properties</li>


<p>

also you need to  config same files in project root 'used when i need configuration outside the Jar  '
</p>
<li>application.properties</li>
<li>database.properties</li>


<p>First if you know OOP and MVC concepts you are good to go else {read about them first }</p>


<p> <strong>Code First </strong> </p>
<p> if need to go and build your database Like old school it's ok go and do it  </p>

<div> <strong> otherwise  under app.models  created file call Admin.java </strong> </div>


<code>
  
        
          package app.models;
          import javax.persistence.Entity;
        import javax.persistence.Id;
        import javax.persistence.Table;
        import java.sql.Timestamp;
    
        import io.ebean.Ebean;
        import io.ebean.Model;
        import io.ebean.annotation.Index;
        @Entity
        @Table(name="admin")
        public class Admin extends Model {
        
        
            @Id
            public long userId;
        
        
            @Index(unique=true)
            public String userName;
        
            public String userPassword;
        
            public Timestamp dateCreated;
        
            public String lastIP;
        
            public String token;
        
            public Timestamp lastLogin;
        
            public String getAPI_token() {
                return API_token;
            }
        
            public void setAPI_token(String API_token) {
                this.API_token = API_token;
            }
        
            public String API_token;
        
            public String getAPI_Key() {
                return API_Key;
            }
        
            public void setAPI_Key(String API_Key) {
                this.API_Key = API_Key;
            }
        
            public String API_Key;
        
            public Admin() {
                super();
            }
        
            public long getUserId() {
                return userId;
            }
        
            public void setUserId(Long userId) {
                this.userId = userId;
            }
        
            public String getUserName() {
                return userName;
            }
        
            public void setUserName(String userName) {
                this.userName = userName;
            }
        
            public String getUserPassword() {
                return userPassword;
            }
        
            public void setUserPassword(String userPassword) {
                this.userPassword = userPassword;
            }
        
            public Timestamp getDateCreated() {
                return dateCreated;
            }
        
            public void setDateCreated(Timestamp dateCreated) {
                this.dateCreated = dateCreated;
            }
        
            public String getLastIP() {
                return lastIP;
            }
        
            public void setLastIP(String lastIP) {
                this.lastIP = lastIP;
            }
        
            public String getToken() {
                return token;
            }
        
            public void setToken(String token) {
                this.token = token;
            }
        
            public Timestamp getLastLogin() {
                return lastLogin;
            }
        
            public void setLastLogin(Timestamp lastLogin) {
                this.lastLogin = lastLogin;
            }
        
            public Admin  finder(long id){
                return Ebean.find(Admin.class , id);
        
            }
        
        
        

</code>
<div><p>  your find this file and it's related files in repo code  </p>
</div>

<p> <strong> database migration  </strong> </p>
<p> if you did't use Mysql go to DBmarge file and change database config to what you are using</p>

<p> than run DBmarge it will create migration file than restart your server you will see the table admin :-) </p>

<code style="background:#ccc">



        public class DBmarge {
           public static void main(String arg[]){
                try {
                    DbMigration dbMigration = DbMigration.create();
                    dbMigration.setPlatform(Platform.MYSQL); // change to your database type
                    dbMigration.generateMigration();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }




</code>


<p> Models Helper and finder </p>
<div>
    
    
    in models we create 2 dir called 
    1 - logic // for CRUD helpers 
    2 - finder // to search and finde 
    


<p> in logic create Admin Helper by creating AdminHelper.java  </p>

<code>
        
      package app.models.logic;
      
      import app.models.Admin;
      import com.cloudsgen.system.core.DataBase.CGModel;
      import com.cloudsgen.system.core.DataBase.ICrud;
      import io.ebean.Ebean;
      import io.vertx.ext.web.RoutingContext;


        
      public class AdminHelper extends CGModel implements ICrud {
      
            //the constractor with RoutingContext
             public AdminHelper(RoutingContext rx)
                {
                    super(rx);
                }
                
      }


</code>

<p><strong> than we add CRUD method add , edit and delete</strong></p>
<code>
 
      @Override
          public void add(Object tClass) {
          if(tClass instanceof Admin)
          {
              Admin c = (Admin) tClass;
              c.save();
  
  
          }
      }
  
      @Override
      public void edit(Object id ) {
          if(id instanceof Admin) {
  
              Admin c = (Admin) id;
  
  
              c.update();
  
          }
      }
  
      @Override
      public void delete(Object id) {
  
  
              Admin c = Ebean.getDefaultServer().find(Admin.class).where().eq("user_id" , id).findOne();
             if(c != null) {
  
  
                 Ebean.getDefaultServer().delete(c);
             }
  
      }


</code>


</div>

<p><strong> email me <a href="mailto:info@sadeem-egypt.com">info@sadeem-egypt.com</a></strong></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>stay tuned&nbsp;</strong></p>
<p>&nbsp;</p>