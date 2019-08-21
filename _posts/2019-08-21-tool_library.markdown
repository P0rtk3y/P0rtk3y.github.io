---
layout: post
title:      "Tool Library "
date:       2019-08-21 05:45:43 +0000
permalink:  tool_library
---

**A Rails App using Action Controller**

Tool Library keeps track of each tool loaned from a Library. A user can login to their account, find their list of tools, and lend them to a community of borrowers. Tool Library uses a web framework called "Rails" to help route requests in the Tool Library application to a database composed of libraries, tools, and borrowers. The data is then returned back to the user in a viewable format. Collectively this framework is known as the the Model-View-Controller (MVC). 

At the core of Tool Library's functionaity is an Action Controller called the "LoansController". A Controller takes data inputted onto the page (through a form), adds the data to a database (the Loan Model), and returns it when requested. For the Tool Library application, the Loan Model is also known as the "join table" because it serves as a middleman that creates relationships between the Tool Model and the Borrower Model. When the LoansController receives an HTTP verb for a "new" loan:

>http://localhost:3000/loans/new


The request will map to the New method in the Controller:


```
  def **new**
    if params[:borrower_id] && @borrower = Borrower.find_by_id(params[:borrower_id])
      @loan = @borrower.loans.build 
    else
      @loan = Loan.new
      @loan.build_borrower 
    end
  end
```


In addition to creating a new loan, a Controller can also define how a tool and a borrower should be associated. The Controller can then render the associated information for the user to see through the User's actions. A summary of each Controller method is provided below to help you as you build your application:

> **index ** : returns a list of all loans  
> 
> **new** : creates a new Loan. This method is called when the user requests a new Loan and allows the user to input data based on the fields of information requested on the form. 
>
> **create ** : adds a new Loan into the database. The user's inputted information from the new method is wrapped into an "envelope" called loan_params. Params have "keys" named after each field with an associated "values" inputted by the user.  If the user's information saves successfully in the database, the user is redirected back to the index to view all loans or the show page for a specific loan.  
>
> **show** : displays a specific loan. For example: @loan = Loan.find(params[:id]) will return the loan associated with the specified :id. This method is not editable. 
> 
> **edit** : displays a specific loan for the user to modify. 
> 
> **update** : called after the edit method to send the edited loan information to the databse.  Update overwrites an existing loan rather than adding a new loan to the database. 
> 
> **delete** : removes a loan from the database by finding the loan and destroying it. For example: Loan.find(params[:id]).destroy will delete the loan associated with the specified :id.  

   
  




