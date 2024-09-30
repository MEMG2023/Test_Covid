# Logistics Tariff Calculator Web App

## Description

This web application allows users to calculate the optimal transport rates for various orders by processing products through different logistics carriers. The application considers several factors such as weight, volume, and product types, and it compares tariffs from multiple carriers (CBL, ONTIME, MRW). 

Additionally, the app provides a comprehensive summary and recommendation on the most cost-effective carrier for the entire shipment or for individual items.

## Key Features

- **Order Processing**: Upload orders in `.csv`, `.xlsx`, or `.xls` formats to calculate shipping costs.
- **Multiple Carriers**: Calculates tariffs from CBL, ONTIME, and MRW, offering optimal solutions based on product dimensions, weight, and carrier-specific surcharges.
- **Pallet Management**: Products are sorted and distributed into pallets, considering the physical constraints of the pallet and product stacking capabilities (e.g., washing machines, combis).
- **Special Products Handling**: Special cases, such as oversized items or products that exceed standard dimensions, are flagged for manual processing.
- **Fuel and Insurance Surcharges**: Fuel surcharges are applied for CBL and ONTIME, while insurance surcharges are factored for ONTIME.
- **Return Calculations**: Users can input SKUs and quantities to calculate return costs based on selected carriers.
- **Custom Recommendations**: Provides recommendations based on the carrier that offers the lowest price for the entire shipment.
- **Logging & Debugging**: Includes detailed logs for troubleshooting, order processing, and debugging information.

## Application Workflow

1. **Upload Order**:
   - Users can upload an order file in `.csv`, `.xls`, or `.xlsx` format.
   - The system processes each product in the order and matches them with data from the product database (`Productos.xlsx`).
   
2. **Carrier Comparison**:
   - Once the order is processed, the system compares the tariffs from CBL, ONTIME, and MRW.
   - Surcharges are applied based on the carrier and fuel rates.
   
3. **Summary**:
   - The app generates a summary of the shipment, displaying the total pallets, XS shipments, and a breakdown of the tariffs per carrier.
   - A recommendation is provided for the most economical carrier for the entire shipment.
   
4. **Return Calculator**:
   - Users can enter the SKU and quantity to calculate return tariffs for individual products.

## Project Structure

├── app.py                  # Main application logic
├── pedido_processor.py      # Functions for processing orders
├── templates/
│   └── index.html           # Frontend HTML template
├── uploads/                 # Directory to store uploaded files
├── Productos.xlsx           # Product catalog containing weights, dimensions, and categories
├── Tarifas_CBL.xlsx         # Tariff rates for CBL
├── Tarifas_ONTIME.xlsx      # Tariff rates for ONTIME
├── Tarifas_MRW.xlsx         # Tariff rates for MRW
├── registros_envio.csv      # Logs of processed shipments
├── README.md                # Documentation file
├── requirements.txt         # Dependencies required for the app

## Requirements

To run this project, you will need:

- Python 3.x
- Flask
- pandas
- openpyxl
- numpy

You can install the necessary dependencies using:
pip install -r requirements.txt

## Usage

1. Clone the repository:
git clone https://github.com/Nambu89/Logistics-Tariff-Calculator-Web-App.git
cd Logistics-Tariff-Calculator-Web-App


2. Set up the environment:
python -m venv env
source env/bin/activate  # Linux/Mac
env\Scripts\activate     # Windows


3. Install the dependencies:
pip install -r requirements.txt

4. Run the application:
python app.py

5. Open the browser and go to `http://127.0.0.1:5000/` to start using the app.

## Future Improvements

- **Enhanced Product Categories**: Expand the logic for other categories of products, including more constraints based on product types.
- **International Shipping Rates**: Add functionality to handle international shipping costs.
- **Machine Learning for Tariff Prediction**: Implement a predictive model based on historical data to optimize tariff selection.
