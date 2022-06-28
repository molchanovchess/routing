## Description. 
In this project we included app-routing module to add navigation on our website.
We also receive data (contacts) from REST API, show contacts in the table and dynamicly generate web pages for selected contacts using contact id for the url path.

## Realization
Project contains
1. **Model** - interface Contact {gender, name, location, email, etc.}
2. **Service** - Contact. Used for receiving data from REST API
3. **routig module**. Paths for components. For SPA navigation we use <a routerLink> tag.
4. - **contact-list** Component. Used for subscribe method to Contact service and displaying data in table.
   - **navbar**, home, about Components - are static data.
   - **contact-details** Component dynamicly generates data for selected component. 

  - To **generate URL** we use contact id 
      **< a routerLink="/contacts/{{contact.login._uuid_}}" >**

  - To **get the the id from URL** we use interface **ParamMap**
  
  this.activatedRoute.paramMap.subscribe((param: ParamMap) => {
      this.contactId = param.get('id');...

  - And at the very end we **generate contact deatails** according to selected contact
