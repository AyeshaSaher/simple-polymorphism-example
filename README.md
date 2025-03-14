# simple-polymorphism-example

// Code your testbench here
// or browse Examples
// polymorphism
// use virtual keyword in parent class 
//  parent class can access child class properties / methods

class parent;
  
  // Declare the function as virtual in the parent class
  virtual function void print();
    $display("We are inside parent class");
  endfunction 
  
endclass: parent


class child extends parent;
  
  // Override the virtual function in the child class
  function void print();
    $display("We are inside child class");
  endfunction
  
endclass: child


module top;
  
  parent p;
  child c;
  
  initial begin 
    p = new();
    c = new();

    // Assign child instance to parent reference
    p = c;

    // This will call the child's print method due to polymorphism
    p.print(); // output: We are inside child class
    c.print(); // output: We are inside child class
  end 
  
endmodule: top


https://edaplayground.com/x/AhbB
