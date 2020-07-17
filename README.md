# dynamic-table
js lib to add search and pagination to tables

# Usage

**Config**

config : {
      get_rows : function used to select rows to do pagination on
          If no function is provided, checks for a config.table element and looks for rows in there to page
 
      box : Empty element that will have page buttons added to it
          If no config.box is provided, but a config.table is, then the page buttons will be added using the table
 
      table : table element to be paginated
          not required if a get_rows function is provided
 
      rows_per_page : number of rows to display per page
          default number is 10
 
      page: page to display
          default page is 1
 
      box_mode: "list", "buttons", or function. determines how the page number buttons are built.
          "list" builds the page index in list format and adds class "pagination" to the ul element. Meant for use with bootstrap
          "buttons" builds the page index out of buttons
          if this field is a function, it will be passed the config object as its only param and assumed to build the page index buttons
 
      page_options: false or [{text: , value: }, ... ] used to set what the dropdown menu options are available, resets rows_per_page value
          false prevents the options from being displayed
          [{text: , value: }, ... ] allows you to customize what values can be chosen, a value of 0 will display all the table's rows.
          the default setup is
            [
                { value: 5,  text: '5'   },
                { value: 10, text: '10'  },
                { value: 20, text: '20'  },
                { value: 50, text: '50'  },
                { value: 100,text: '100' },
                { value: 0,  text: 'All' }
            ]
 
      active_class: set the class for page buttons to have when active.
           defaults to "active"
 
      disable: true or false, shows all rows of the table and hides pagination controlls if set to true.
 
      tail_call: function to be called after paginator is done.
 
  }
 
