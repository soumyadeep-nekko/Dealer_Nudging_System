# Dealer_Nudging_System

Overview
The Dealer Nudging System (DNS) is a comprehensive platform designed to help OEMs (Original Equipment Manufacturers) incentivize dealers to sell specific products through various schemes and offers. This improved version focuses on mobile phone dealers but is designed with a flexible schema that can accommodate other product categories.

Key Features
Granular Data Model: Captures detailed product specifications, complex scheme structures, and various incentive types
PDF Extraction: Automatically extracts scheme details from PDF documents
Interactive Dashboard: Provides comprehensive insights with advanced visualizations
Scheme Explorer: Allows detailed exploration of all schemes and their parameters
Editable Tables: Supports editing of scheme details with approval workflow
Sales Simulation: Enhanced simulation tool to model different sales scenarios
Approval Workflow: Structured process for reviewing and approving scheme changes
System Architecture
The system consists of the following components:

Database: SQLite database with a comprehensive schema for storing all scheme and sales data
PDF Processor: Python module for extracting structured data from scheme PDFs
Streamlit App: Web interface for interacting with the system
AWS Integration: Optional integration with AWS Bedrock (Claude) and Textract for enhanced PDF processing
Setup Instructions
Install Dependencies:

pip install streamlit plotly pandas boto3 PyPDF2 Pillow pymupdf
Configure AWS Credentials (Optional):

Place your AWS credentials in secrets.json file
Required for enhanced PDF extraction using AWS Textract and Claude
Initialize the System:

python setup.py
This will:

Create necessary directories
Initialize the database
Copy sample PDFs to the schemes directory
Set up the secrets file
Process Scheme PDFs:

python pdf_processor.py
This will:

Extract data from all PDFs in the schemes directory
Populate the database with scheme details
Create sample dealers and sales data
Run the Application:

streamlit run app.py
Database Schema
The system uses a comprehensive SQLite database with the following tables:

schemes: Stores basic scheme information
products: Stores product details with granular specifications
dealers: Stores dealer information
scheme_products: Links schemes to products with incentive details
payout_slabs: Stores quantity-based incentive slabs
scheme_rules: Stores scheme rules and conditions
dealer_targets: Stores targets assigned to dealers
sales_transactions: Records sales transactions
exchange_transactions: Records device exchange/upgrade transactions
scheme_approvals: Tracks approval workflow for schemes
scheme_parameters: Stores additional scheme parameters
bundle_offers: Stores bundle offer details
Key Improvements
Enhanced Data Model:

Added support for RAM, storage, connectivity, and other detailed attributes
Implemented flexible payout structures (fixed, percentage, slab-based)
Added support for bundle offers and exchange programs
Improved Dashboard:

Added comprehensive visualizations for scheme effectiveness
Implemented regional performance tracking
Added product performance heatmap
Enhanced dealer performance comparison
Advanced Features:

Implemented approval workflow for scheme edits
Enhanced sales simulation with comparative analysis
Added support for bundle offers and upgrade programs
Implemented verification workflow for sales transactions
Technical Improvements:

Optimized PDF extraction process
Implemented AWS integration for enhanced text extraction
Designed responsive UI with modern styling
Added unique keys to all Plotly charts to prevent duplicate ID errors
Usage Guide
Dashboard
The dashboard provides a comprehensive overview of:

Active schemes and products
Sales performance over time
Dealer performance comparison
Product performance heatmap
Scheme effectiveness analysis
Regional performance visualization
Scheme Explorer
Allows you to:

Browse all schemes with detailed filtering
View scheme details including products, incentives, and rules
Approve or reject pending schemes
Product Catalog
Provides:

Comprehensive product listing with specifications
Filtering by category, subcategory, and status
Product management capabilities
Dealer Management
Enables:

Dealer listing and filtering
Dealer performance tracking
Dealer status management
Sales Tracker
Offers:

Transaction listing and filtering
Verification workflow for transactions
Sales metrics and analysis
Upload Scheme
Allows:

PDF upload for new schemes
Automatic extraction of scheme details
Manual editing of extracted data
Submission for approval
Approval Center
Provides:

Listing of pending approvals
Review and approval/rejection workflow
Editing of scheme details before approval
Sales Simulation
Enables:

Simulation of sales scenarios
Comparison of different schemes
Analysis of dealer economics
Recording of simulated sales
Extensibility
The system is designed to be extensible in the following ways:

Additional Product Categories: The schema can accommodate various product types beyond mobile phones
New Scheme Types: The flexible scheme structure supports various incentive models
Integration Points: The system can be integrated with other systems through API endpoints
Customizable Visualizations: The dashboard can be extended with additional visualizations
Troubleshooting
PDF Extraction Issues:

Ensure PDFs are text-based and not scanned images
For scanned PDFs, AWS Textract integration provides better results
Check AWS credentials if using Textract
AWS Integration:

Verify AWS credentials in secrets.json
Ensure the specified region matches your AWS setup
Check that the inference profile ARN is correct for Claude
Database Issues:

If database becomes corrupted, delete dealer_schemes.db and run setup.py again
Use the SQLite browser to inspect database contents if needed
Streamlit Interface:

If charts don't render, check for duplicate element IDs
Restart the application if the interface becomes unresponsive
Future Enhancements
Multi-user Authentication: Add user roles and permissions
Mobile App Integration: Develop companion mobile app for dealers
Advanced Analytics: Implement predictive analytics for sales forecasting
API Endpoints: Create REST API for integration with other systems
Notification System: Add email/SMS notifications for scheme updates and approvals
