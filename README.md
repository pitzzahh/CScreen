**C-screen** is a text-base UI on java console, you can now easily design your console program using c-screen with the help of several components.

_download here:_ https://github.com/soybean15/CScreen/releases

_Update as of August 4 2022, 1:20pm_

_Since Box-window is not working on default on some OS, I added a method where you can choose between normal character and box-window character_

**Normal Characters:**
```java
    //normal character
    Screen screen = new Screen(20,40,true);
    //screen.useBoxSet();
    screen.addTitle("Sample Screen",Position.START);
    screen.display();
    
    /*
    sample output
    +--------------------------------------+
    |Sample Screen                         |
    |+------------------------------------+|
    */
```
**Box-Window Characters:**
```java
    //box-window character
    Screen screen = new Screen(20,40,true);
    screen.useBoxSet();
    screen.addTitle("Sample Screen",Position.START);
    screen.display();
    
    /*
    sample output
    ╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
    │Sample Screen                         │
    │╭┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮│

    */
```

**C-Screen features:**

**1. Screen**: a framelike interface where you can put multiple components.
        
**Sample code:**

```java
        
        
        Screen screen = new Screen(20,40,true);
        screen.addTitle("Sample Screen",Position.START);
        screen.display();
        
        
        /*the 3 parameters on the constructor are the following:
        -width - width of screen
        -height - height of screen
        -hasBorder - add inner border if true
        */
```
                
**Sample output:**
        
![image](https://user-images.githubusercontent.com/75112014/182511031-ec59293c-8cd0-4297-8e9a-47abb9dfba84.png)




**2. Box:** a rectangular component you can Put inside the Screen.

**Sample code:**


```java
      Screen screen = new Screen(20,40,true);
      screen.addTitle("Sample Screen",Position.START);     

      Box box = new Box(3,3);
      box.setHeight(5);
      box.setWidth(30);
      
      //place component inside the screen
      box.place(screen);
      
      //display screen
      screen.display();
      
```
      
**Sample output:**

![image](https://user-images.githubusercontent.com/75112014/182512062-a3f041f9-9071-47e0-a934-bdf03e145f27.png)


**3.TextBox:** A box component with String inside

**Sample code:**

```java
        
      Screen screen = new Screen(20,40,true);
      screen.addTitle("Sample Screen",Position.START);


      TextBox textBox = new TextBox(3,3);
      textBox.setText("Sample text");
      textBox.setHeight(5);
      textBox.setWidth(30);

      //place component inside the screen
      textBox.place(screen);

      //display screen
      screen.display();
      
```


**Sample output:**
  
  
![image](https://user-images.githubusercontent.com/75112014/182512666-f2a78982-07ca-43b7-baee-4b997efb1afc.png)

      
      
      
      
**4. Label** : String you can put inside the screen.

**Sample code:**

```java

      Screen screen = new Screen(20,40,true);
      screen.addTitle("Sample Screen",Position.START);


      Label label = new Label(3,3);
      label.setText("Sample Label");

      //place component inside the screen
      label.place(screen);

      //display screen
      screen.display();
      
 ```
  
  
**Sample output:**


![image](https://user-images.githubusercontent.com/75112014/182512590-daee429e-7923-496c-9374-8b92a2e0f0e4.png)






**5. Button:** Buttonlike component which is good to have if you have multiple option in your code.

**Sample code:**


```java
      Screen screen = new Screen(20,40,true);
      screen.addTitle("Sample Screen",Position.START);


      Button button1 = new Button(3,3);
      button1.setText("Button1");
      //place component inside the screen
      button1.place(screen);
      
      Button button2 = new Button(6,3, "Button2");
      //place component inside the screen
      button2.place(screen);

      //display screen
      screen.display();
      
```
      
      
**Sample output:**


![image](https://user-images.githubusercontent.com/75112014/182513091-be1fa938-c97b-4975-b293-65a8ae5c2654.png)






**6. CList**: component to help your list looks more neat


**Sample code:**


```java
        CList list = new CList();
        list.useBoxSet();
        list.setWidth(20);
        list.setTitle("Fruits",Position.CENTER);

        list.addItem("Apple");
        list.addItem("Banana");
        list.addItem("Mango");
        list.addItem("Banana");

        list.display();


```

**Sample output:**


![image](https://user-images.githubusercontent.com/75112014/182986520-7f5b1a4c-d022-417d-bf77-bb85eef9d985.png)


**CList Functions**


**setWidth(int width)** - setting width of rectangular border of list. If not set, it will base on the longest size of the String inside the list.

**setTitle(String title,Position pos)** - Add title on the list, there are three choice for position _POSITION.START, POSITION.CENTER, POSITION.END_.

**addItem(String item)** - add item on the list.

**getItem(int index)** - get item on the list by index.

**remove(int index)** - remove item on the list by index.

**set(int index, String item)** - edit/update item by index.





**7. CTable**: easiest way to output your data on console, just pass your 2d array and you got yourself a neat and instant table.

**Sample code:**

```java

        CTable table = new CTable(header);
        table.useBoxSet();
        table.setAlignment(Position.CENTER);
        table.hasSeparator(true);
        table.addRow(new String[]{"f011", "Fries", "10", "70.00"});
        table.addRow(new String[]{"b212", "Burger", "10", "30.00"});
        table.addRow(new String[]{"fc11", "Fried Chicken", "10", "110.00"});
        table.addRow(new String[]{"f011", "Fries", "10", "70.00"});
        table.addRow(new String[]{"s930", "Sundae", "10", "30.00"});
        table.display();

```


**Sample output:**


![image](https://user-images.githubusercontent.com/75112014/182984096-ff349dd6-af0b-422b-a891-1474c0b3de6a.png)


**CTable Functions**

 
**addList(List<List<String>> arr)** - Add 2d array on CTable.
    
**addRow(String[] row)** - Add row inside the table.
    
**getRow(int index)** - get all the value of selected row, index is the position of desired row.
    
**getColumn(int index)** - get all the value of selected column, index is the position of desired column.
    
**removeRow(int index)** - remove selected row by index
    
**getCell(int row, int column)** - get cell item inside the table.
    
**setCell(int row, int column,String str)** - edit/update the selected cell in the table.
 
_Hope you like it..enjoy._












        
        
        



        
