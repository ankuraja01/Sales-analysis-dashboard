# Sales-analysis-dashboard
import streamlit as st
import pandas as pd

st.title("📊 Sales Analysis Dashboard")

# CSV File Read
df = pd.read_csv("sales_data.csv")

# Total Sales
total_sales = df["Sales"].sum()

# Total Profit
total_profit = df["Profit"].sum()

# Total Orders
total_orders = len(df)

# Show Metrics
st.metric("Total Sales", total_sales)
st.metric("Total Profit", total_profit)
st.metric("Total Orders", total_orders)

# Sales by Category
st.subheader("Sales by Category")
st.bar_chart(df.groupby("Category")["Sales"].sum())

# Sales by Region
st.subheader("Sales by Region")
st.bar_chart(df.groupby("Region")["Sales"].sum())

# Data Table
st.subheader("Sales Data")
st.dataframe(df)
