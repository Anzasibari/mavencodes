import java.util.Scanner;

// INTERFACE
interface IProduct {

int GetTotalProductsSold();

double GetAverageProductSold();

String GetMostPopularProduct();
}

// PRODUCT CLASS
class Product implements IProduct {

private String[] productNames;
private int[][] productSales;

// Constructor
public Product(String[] productNames, int[][] productSales) {

this.productNames = productNames;
this.productSales = productSales;
}

// Calculate total products sold
@Override
public int GetTotalProductsSold() {

int total = 0;

for (int i = 0; i < productSales.length; i++) {

for (int j = 0; j < productSales[i].length; j++) {

total += productSales[i][j];
}
}

return total;
}

// Calculate average products sold
@Override
public double GetAverageProductSold() {

int total = GetTotalProductsSold();

int numberOfSales = 0;

for (int i = 0; i < productSales.length; i++) {

numberOfSales += productSales[i].length;
}

if (numberOfSales == 0) {
return 0;
}

return (double) total / numberOfSales;
}

// Find most popular product
@Override
public String GetMostPopularProduct() {

int highestSales = -1;

String popularProduct = "";

for (int i = 0; i < productSales.length; i++) {

int productTotal = 0;

for (int j = 0; j < productSales[i].length; j++) {

productTotal += productSales[i][j];
}

if (productTotal > highestSales) {

highestSales = productTotal;

popularProduct = productNames[i];
}
}

return popularProduct + " (" + highestSales + ")";
}
}

// PRINT PRODUCT CLASS
class PrintProduct {

// Print total sales
public void PrintTotalSales(Product product) {

System.out.println("TOTAL PRODUCT SALES: "
+ product.GetTotalProductsSold());
}

// Print average sales
public void PrintAverageSales(Product product) {

System.out.printf("AVERAGE PRODUCT SALES: %.0f%n",
product.GetAverageProductSold());
}

// Print most popular product
public void PrintMostPopularProduct(Product product) {

System.out.println("MOST POPULAR PRODUCT: "
+ product.GetMostPopularProduct());
}

// Print complete report
public void PrintReport(Product product) {

System.out.println();

System.out.println("PRODUCT SALES REPORT - 2026");

System.out.println("****************************************");

PrintTotalSales(product);

PrintAverageSales(product);

PrintMostPopularProduct(product);

System.out.println("****************************************");
}
}

// MAIN CLASS
public class Main {

public static void main(String[] args) {

Scanner input = new Scanner(System.in);

// Single-dimensional array
String[] productNames = {

"Cozy Nights Monarch mattress",

"Restonic Barbados mattress",

"Sealy Phuket mattress"
};

// Two-dimensional array
int[][] productSales = new int[3][3];

// Enter sales information
for (int i = 0; i < productNames.length; i++) {

for (int j = 0; j < 3; j++) {

System.out.print(
"Enter number of sales for month "
+ (j + 1)
+ " for "
+ productNames[i]
+ ": "
);

productSales[i][j] = input.nextInt();
}

System.out.println();
}

// Create Product object
Product product = new Product(
productNames,
productSales
);

// Create PrintProduct object
PrintProduct report = new PrintProduct();

// Display report
report.PrintReport(product);

input.close();
}
}
