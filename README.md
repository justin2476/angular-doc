-------------------
To start a project
-------------------

=>ng new Project_name

=>ng serve

app will start running on port number 4200 by default 

directly edit app.component.html

component are like modules which can be generated by

=>ng generate component name

each component will be in a folder with html, css and ts file 
in component.ts file. 

// selector tag can be used 
@Component({
  selector: 'app-gov-html',
  templateUrl: './gov-html.component.html',
  styleUrls: ['./gov-html.component.css']
})

now we can render above compoment by using selector, 
that is <app-gov-html>

--------
Routing
--------
  
Set the router path and component in routing module that is 
app-routing.module.ts

const routes: Routes = [
  {
  path: 'login',
  component: LoginComponent
}
];

To set route in ts file or html of component 

Set routing in component.ts file
 
import { Router } from '@angular/router';
 constructor(private router: Router) { }
 this.router.navigate(['/Dashboard']);

Set in html file 

 <a routerLink="signup" routerLinkActive="active">click here</a>

To set where to render should defined in app.component.html 

<router-outlet></router-outlet>

----------
Component
----------

Typescript for dealing with data is in component. Variables in component can be accessed in html by {{VariableName}}

---------
Services
---------

Services are defined to call backend api,  one service file is good enough for all the APIs.
generate the service by, ng generate service nameOfservice;

export class ApiService {
  url = 'https://jsonplaceholder.typicode.com/todos/1';
  constructor(private http: HttpClient) { }

//getWork is function
public getWork()  {
  return this.http.get(this.url);
  }
}

We can now use getWork function in any component by importing ApiService and declaring it in the constructer 

