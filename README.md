# Dealer Nudging System (DNS)

The **Dealer Nudging System (DNS)** is a comprehensive platform designed to help OEMs (Original Equipment Manufacturers) incentivize dealers to promote and sell specific products through structured schemes and offers. While the current version is optimized for **mobile phone dealers**, the architecture is flexible enough to accommodate other product categories.

---

## 🚀 Key Features

- **Granular Data Model**: Detailed product specs, complex scheme structures, multiple incentive types
- **PDF Extraction**: Auto-extracts scheme details from PDF documents
- **Interactive Dashboard**: Visual insights into performance and effectiveness
- **Scheme Explorer**: Explore schemes, incentives, rules, and structures
- **Editable Tables**: Update scheme details with an approval workflow
- **Sales Simulation**: Model sales scenarios and compare outcomes
- **Approval Workflow**: Review and approve scheme modifications

---

## 🏗️ System Architecture

- **Database**: SQLite schema for storing all scheme and sales data
- **PDF Processor**: Python module to extract structured data from PDFs
- **Streamlit App**: User-friendly web interface
- **AWS Integration (Optional)**: Enhanced extraction via AWS Textract & Bedrock (Claude)

---

## ⚙️ Setup Instructions

### 1. Install Dependencies

```bash
pip install streamlit plotly pandas boto3 PyPDF2 Pillow pymupdf
2. Configure AWS Credentials (Optional)
Create a secrets.json file for AWS Textract and Claude integration.

json
Copy
Edit
{
  "aws_access_key_id": "YOUR_KEY",
  "aws_secret_access_key": "YOUR_SECRET",
  "region_name": "YOUR_REGION"
}
3. Initialize the System
bash
Copy
Edit
python setup.py
This will:

Create necessary directories

Initialize the database

Copy sample PDFs to the schemes directory

Set up the secrets file

4. Process Scheme PDFs
bash
Copy
Edit
python pdf_processor.py
This will:

Extract data from all PDFs in the schemes folder

Populate the database with scheme details

Create sample dealers and sales data

5. Run the Application
bash
Copy
Edit
streamlit run app.py
🗄️ Database Schema
schemes: Basic scheme info

products: Product specifications

dealers: Dealer information

scheme_products: Product–scheme mapping with incentives

payout_slabs: Quantity-based incentives

scheme_rules: Scheme conditions and logic

dealer_targets: Dealer-specific goals

sales_transactions: Records of sales

exchange_transactions: Device upgrade/exchange records

scheme_approvals: Approval workflow records

scheme_parameters: Additional scheme metadata

bundle_offers: Bundle-based promotions

📊 Usage Guide
Dashboard
Active schemes & products

Sales performance trends

Dealer & product comparisons

Regional analytics

Scheme Explorer
Browse, filter, and inspect schemes

View linked products, incentives, and rules

Approve/reject schemes

Product Catalog
Detailed specs and filtering

Add/edit product entries

Dealer Management
Track dealer performance and status

Sales Tracker
List & filter sales transactions

Verify sales activity

Upload Scheme
Upload scheme PDFs

Auto-extract and manually edit

Submit for approval

Approval Center
Review pending changes

Approve/reject/edit schemes

Sales Simulation
Model scenarios

Compare scheme effectiveness

Record simulated performance

🧱 Extensibility
Product Categories: Add new categories like tablets, accessories, etc.

Incentive Models: Fixed, percentage, slabs, bundles, exchanges

Integrations: REST APIs for external systems

Visualizations: Custom dashboards for deeper analytics

🛠 Troubleshooting
PDF Extraction
Ensure PDFs are text-based

For scanned PDFs, enable AWS Textract

Check AWS credentials and region settings

Database
If corrupted, delete dealer_schemes.db and re-run setup.py

Use SQLite browser for manual inspection

Streamlit Interface
Restart if unresponsive

Avoid duplicate chart IDs

🧭 Future Enhancements
Multi-user authentication and permissions

Mobile app for dealers

Predictive analytics and forecasting

REST API for external integration

Email/SMS notification system

👥 Contributors
Made with ❤️ by the Nekko Team

📄 License
This project is licensed under the MIT License.

💬 Feedback & Contributions
Pull requests and suggestions are welcome! For major changes, please open an issue first to discuss what you’d like to change.
