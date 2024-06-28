# Property Rental Management System

## Overview

This project implements a property rental management system in DAML. The system allows property owners to list properties, tenants to rent properties, and property managers to oversee rental contracts.

## Project Structure

- **PropertyRental.daml**: Contains the templates and contracts for the property rental management system.
- **PropertyRentalTest.daml**: Contains the happy path and unhappy path test scripts.
- **MainTest.daml**: Contains the main test script that runs all individual test cases.
- **SetupPropertyRental.daml**: Contains the setup for the daml navigator 
## Key Concepts

### Templates

1. **PropertyListing**
    - Represents a property listed by an owner.
    - **Signatory**: Property owner.
    - **Observer**: Specified observer.
    - **Key**: Combination of property ID and owner.
    - **Maintainer**: Property owner.
    - **Choices**:
        - `UpdateStatus`: Update the status of the property. Consuming choice.

2. **RentalAgreementContract**
    - Represents a rental agreement between a property owner and a tenant.
    - **Signatory**: Property owner and tenant.
    - **Observer**: Property owner.
    - **Key**: Combination of agreement ID and property owner.
    - **Maintainer**: Property owner.
    - **Choices**:
        - `StartRental`: Start the rental period. Consuming choice.
        - `MakePayment`: Make a payment for the rent. Consuming choice.
        - `EndRental`: End the rental agreement. Consuming choice.
        - `MaintenanceRequest`: Request maintenance for the property. Non-consuming choice.

### Custom Data Types

- `PropertyStatus`: Represents the status of a property (Available, Rented, Maintenance).
- `PaymentStatus`: Represents the status of a payment (Pending, Completed).

### Custom Records

- `Property`: Contains details about a property.
- `RentalAgreement`: Contains details about a rental agreement.

## Testing

### Happy Path Testing

1. **Test Property Listing and Updating Status**
2. **Test Rental Agreement Creation and Payment**
3. **Test Ending Rental Agreement**

### Unhappy Path Testing

1. **Test Invalid Property Status Update**
2. **Test Invalid Rental Start Date**
3. **Test Invalid Payment Amount**

### Modularized Testing Scripts

- **Main Test Script**: Runs all happy and unhappy path test cases.

## How to Run

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   daml build
   daml test
2. **Run Navigator**:
   ```bash
   daml build
   daml start
