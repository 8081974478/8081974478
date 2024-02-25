import java.util.ArrayList;
import java.util.List;

class Product {
    private String name;
    private double price;
    private int quantity;

    public Product(String name, double price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}

class ShoppingCart {
    private List<Product> items;

    public ShoppingCart() {
        items = new ArrayList<>();
    }

    public void addItem(Product product) {
        items.add(product);
    }

    public double getTotal() {
        double total = 0.0;
        for (Product item : items) {
            total += item.getPrice() * item.getQuantity();
        }
        return total;
    }
}

public class EcommerceWebsite {
    public static void main(String[] args) {
        // Creating some products
        Product product1 = new Product("Laptop", 999.99, 2);
        Product product2 = new Product("Smartphone", 599.99, 3);

        // Adding products to the shopping cart
        ShoppingCart cart = new ShoppingCart();
        cart.addItem(product1);
        cart.addItem(product2);

        // Calculating total price
        double totalPrice = cart.getTotal();
        System.out.println("Total price: $" + totalPrice);
    }
}
