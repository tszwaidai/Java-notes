# Arrays

```java
package com.hspedu.java_Senior;

import java.util.Arrays;
import java.util.Comparator;

public class Homework05 {
    public static void main(String[] args) {
        int[] arr = {1,-1,3,5,8};
        Book[] book = new Book[4];
        book[0] = new Book("c++编程",56);
        book[1] = new Book("西游记",89);
        book[2] = new Book("电子技术基础",85);
        book[3] = new Book("红楼梦",100);

        //price排序
        Arrays.sort(book, new Comparator<Book>() {
            @Override
            public int compare(Book o1, Book o2) {
                Book book1 = (Book) o1;
                Book book2 = (Book) o2;
                double priceVal = book2.getPrice() - book1.getPrice();
                if (priceVal > 0){
                    return 1;
                } else if (priceVal < 0) {
                    return -1;
                }
                else{
                    return 0;
                }

            }
        });
        System.out.println(Arrays.toString(book));
    }

}

class  Book{
    private String name;
    private double price;

    public Book(String name, double price) {
        this.name = name;
        this.price = price;
    } //构造器

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", price=" + price +
                '}';
    }
}


输出 [Book{name='红楼梦', price=100.0}, Book{name='西游记', price=89.0}, Book{name='电子技术基础', price=85.0}, Book{name='c++编程', price=56.0}]

```

