import React, { useState, useEffect } from 'react';
import { Plus, Search, Edit, Trash2, Eye, FileText, ShoppingCart, Package, CreditCard, Users, Building2, TrendingUp, DollarSign } from 'lucide-react';

const SalesPurchaseApp = () => {
  // State Management
  const [activeTab, setActiveTab] = useState('dashboard');
  const [customers, setCustomers] = useState([]);
  const [suppliers, setSuppliers] = useState([]);
  const [products, setProducts] = useState([]);
  const [sales, setSales] = useState([]);
  const [purchases, setPurchases] = useState([]);
  const [payments, setPayments] = useState([]);
  const [receipts, setReceipts] = useState([]);

  // Modal States
  const [showModal, setShowModal] = useState(false);
  const [modalType, setModalType] = useState('');
  const [editingItem, setEditingItem] = useState(null);

  // Form States
  const [customerForm, setCustomerForm] = useState({
    name: '', email: '', phone: '', address: '', gst: ''
  });
  
  const [supplierForm, setSupplierForm] = useState({
    name: '', email: '', phone: '', address: '', gst: ''
  });
  
  const [productForm, setProductForm] = useState({
    name: '', category: '', price: '', stock: '', unit: '', minStock: ''
  });
  
  const [saleForm, setSaleForm] = useState({
    customerId: '', date: '', items: [{ productId: '', quantity: '', rate: '', amount: '' }], 
    subtotal: 0, tax: 0, total: 0, paidAmount: 0, dueAmount: 0
  });
  
  const [purchaseForm, setPurchaseForm] = useState({
    supplierId: '', date: '', items: [{ productId: '', quantity: '', rate: '', amount: '' }], 
    subtotal: 0, tax: 0, total: 0, paidAmount: 0, dueAmount: 0
  });
  
  const [paymentForm, setPaymentForm] = useState({
    type: 'payment', entityId: '', entityType: 'customer', amount: '', date: '', method: 'cash', reference: ''
  });

  // Initialize with sample data
  useEffect(() => {
    const sampleCustomers = [
      { id: 1, name: 'John Doe', email: 'john@email.com', phone: '9876543210', address: '123 Main St', gst: 'GST123456789' },
      { id: 2, name: 'Jane Smith', email: 'jane@email.com', phone: '9876543211', address: '456 Oak Ave', gst: 'GST987654321' }
    ];
    
    const sampleSuppliers = [
      { id: 1, name: 'ABC Supplies', email: 'abc@supplies.com', phone: '9876543212', address: '789 Industrial Rd', gst: 'GST555666777' },
      { id: 2, name: 'XYZ Materials', email: 'xyz@materials.com', phone: '9876543213', address: '321 Factory St', gst: 'GST111222333' }
    ];
    
    const sampleProducts = [
      { id: 1, name: 'Widget A', category: 'Electronics', price: 100, stock: 50, unit: 'pcs', minStock: 10 },
      { id: 2, name: 'Widget B', category: 'Electronics', price: 150, stock: 30, unit: 'pcs', minStock: 5 },
      { id: 3, name: 'Component C', category: 'Parts', price: 25, stock: 100, unit: 'pcs', minStock: 20 }
    ];
    
    setCustomers(sampleCustomers);
    setSuppliers(sampleSuppliers);
    setProducts(sampleProducts);
  }, []);

  // Helper Functions
  const generateId = () => Date.now();
  
  const formatCurrency = (amount) => `₹${parseFloat(amount || 0).toFixed(2)}`;
  
  const resetForms = () => {
    setCustomerForm({ name: '', email: '', phone: '', address: '', gst: '' });
    setSupplierForm({ name: '', email: '', phone: '', address: '', gst: '' });
    setProductForm({ name: '', category: '', price: '', stock: '', unit: '', minStock: '' });
    setSaleForm({
      customerId: '', date: '', items: [{ productId: '', quantity: '', rate: '', amount: '' }], 
      subtotal: 0, tax: 0, total: 0, paidAmount: 0, dueAmount: 0
    });
    setPurchaseForm({
      supplierId: '', date: '', items: [{ productId: '', quantity: '', rate: '', amount: '' }], 
      subtotal: 0, tax: 0, total: 0, paidAmount: 0, dueAmount: 0
    });
    setPaymentForm({
      type: 'payment', entityId: '', entityType: 'customer', amount: '', date: '', method: 'cash', reference: ''
    });
    setEditingItem(null);
  };

  // Modal Controls
  const openModal = (type, item = null) => {
    setModalType(type);
    setEditingItem(item);
    if (item) {
      switch (type) {
        case 'customer':
          setCustomerForm(item);
          break;
        case 'supplier':
          setSupplierForm(item);
          break;
        case 'product':
          setProductForm(item);
          break;
        default:
          break;
      }
    }
    setShowModal(true);
  };

  const closeModal = () => {
    setShowModal(false);
    resetForms();
  };

  // CRUD Operations
  const handleSaveCustomer = () => {
    if (editingItem) {
      setCustomers(customers.map(c => c.id === editingItem.id ? { ...customerForm, id: editingItem.id } : c));
    } else {
      setCustomers([...customers, { ...customerForm, id: generateId() }]);
    }
    closeModal();
  };

  const handleSaveSupplier = () => {
    if (editingItem) {
      setSuppliers(suppliers.map(s => s.id === editingItem.id ? { ...supplierForm, id: editingItem.id } : s));
    } else {
      setSuppliers([...suppliers, { ...supplierForm, id: generateId() }]);
    }
    closeModal();
  };

  const handleSaveProduct = () => {
    const productData = {
      ...productForm,
      price: parseFloat(productForm.price),
      stock: parseInt(productForm.stock),
      minStock: parseInt(productForm.minStock)
    };
    
    if (editingItem) {
      setProducts(products.map(p => p.id === editingItem.id ? { ...productData, id: editingItem.id } : p));
    } else {
      setProducts([...products, { ...productData, id: generateId() }]);
    }
    closeModal();
  };

  // Sale/Purchase Item Management
  const addItem = (form, setForm) => {
    setForm({
      ...form,
      items: [...form.items, { productId: '', quantity: '', rate: '', amount: '' }]
    });
  };

  const removeItem = (form, setForm, index) => {
    const newItems = form.items.filter((_, i) => i !== index);
    setForm({ ...form, items: newItems });
    calculateTotal({ ...form, items: newItems }, setForm);
  };

  const updateItem = (form, setForm, index, field, value) => {
    const newItems = [...form.items];
    newItems[index] = { ...newItems[index], [field]: value };
    
    if (field === 'productId') {
      const product = products.find(p => p.id === parseInt(value));
      if (product) {
        newItems[index].rate = product.price;
      }
    }
    
    if (field === 'quantity' || field === 'rate') {
      newItems[index].amount = parseFloat(newItems[index].quantity || 0) * parseFloat(newItems[index].rate || 0);
    }
    
    const updatedForm = { ...form, items: newItems };
    setForm(updatedForm);
    calculateTotal(updatedForm, setForm);
  };

  const calculateTotal = (form, setForm) => {
    const subtotal = form.items.reduce((sum, item) => sum + parseFloat(item.amount || 0), 0);
    const tax = subtotal * 0.18; // 18% GST
    const total = subtotal + tax;
    const dueAmount = total - parseFloat(form.paidAmount || 0);
    
    setForm(prev => ({
      ...prev,
      subtotal: subtotal.toFixed(2),
      tax: tax.toFixed(2),
      total: total.toFixed(2),
      dueAmount: dueAmount.toFixed(2)
    }));
  };

  // Update stock when saving sales/purchases
  const updateStock = (items, type) => {
    setProducts(prevProducts => {
      return prevProducts.map(product => {
        const item = items.find(i => parseInt(i.productId) === product.id);
        if (item) {
          const quantity = parseInt(item.quantity);
          if (type === 'sale') {
            return { ...product, stock: Math.max(0, product.stock - quantity) };
          } else if (type === 'purchase') {
            return { ...product, stock: product.stock + quantity };
          }
        }
        return product;
      });
    });
  };

  const handleSaveSale = () => {
    const saleData = {
      ...saleForm,
      id: generateId(),
      invoiceNo: `INV-${generateId().toString().slice(-6)}`,
      customer: customers.find(c => c.id === parseInt(saleForm.customerId))
    };
    
    setSales([...sales, saleData]);
    updateStock(saleForm.items, 'sale');
    closeModal();
  };

  const handleSavePurchase = () => {
    const purchaseData = {
      ...purchaseForm,
      id: generateId(),
      billNo: `BILL-${generateId().toString().slice(-6)}`,
      supplier: suppliers.find(s => s.id === parseInt(purchaseForm.supplierId))
    };
    
    setPurchases([...purchases, purchaseData]);
    updateStock(purchaseForm.items, 'purchase');
    closeModal();
  };

  const handleSavePayment = () => {
    const paymentData = {
      ...paymentForm,
      id: generateId(),
      entity: paymentForm.entityType === 'customer' 
        ? customers.find(c => c.id === parseInt(paymentForm.entityId))
        : suppliers.find(s => s.id === parseInt(paymentForm.entityId))
    };
    
    if (paymentForm.type === 'payment') {
      setPayments([...payments, paymentData]);
    } else {
      setReceipts([...receipts, paymentData]);
    }
    closeModal();
  };

  // Calculate dashboard metrics
  const totalSales = sales.reduce((sum, sale) => sum + parseFloat(sale.total || 0), 0);
  const totalPurchases = purchases.reduce((sum, purchase) => sum + parseFloat(purchase.total || 0), 0);
  const totalReceivables = sales.reduce((sum, sale) => sum + parseFloat(sale.dueAmount || 0), 0);
  const totalPayables = purchases.reduce((sum, purchase) => sum + parseFloat(purchase.dueAmount || 0), 0);
  const lowStockProducts = products.filter(p => p.stock <= p.minStock);

  // Render Functions
  const renderDashboard = () => (
    <div className="p-6">
      <h2 className="text-3xl font-bold mb-6 text-gray-800">Dashboard</h2>
      
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
        <div className="bg-gradient-to-r from-blue-500 to-blue-600 text-white p-6 rounded-xl shadow-lg">
          <div className="flex items-center justify-between">
            <div>
              <p className="text-blue-100">Total Sales</p>
              <p className="text-3xl font-bold">{formatCurrency(totalSales)}</p>
            </div>
            <TrendingUp className="w-12 h-12 text-blue-200" />
          </div>
        </div>
        
        <div className="bg-gradient-to-r from-green-500 to-green-600 text-white p-6 rounded-xl shadow-lg">
          <div className="flex items-center justify-between">
            <div>
              <p className="text-green-100">Total Purchases</p>
              <p className="text-3xl font-bold">{formatCurrency(totalPurchases)}</p>
            </div>
            <ShoppingCart className="w-12 h-12 text-green-200" />
          </div>
        </div>
        
        <div className="bg-gradient-to-r from-yellow-500 to-yellow-600 text-white p-6 rounded-xl shadow-lg">
          <div className="flex items-center justify-between">
            <div>
              <p className="text-yellow-100">Receivables</p>
              <p className="text-3xl font-bold">{formatCurrency(totalReceivables)}</p>
            </div>
            <DollarSign className="w-12 h-12 text-yellow-200" />
          </div>
        </div>
        
        <div className="bg-gradient-to-r from-red-500 to-red-600 text-white p-6 rounded-xl shadow-lg">
          <div className="flex items-center justify-between">
            <div>
              <p className="text-red-100">Payables</p>
              <p className="text-3xl font-bold">{formatCurrency(totalPayables)}</p>
            </div>
            <CreditCard className="w-12 h-12 text-red-200" />
          </div>
        </div>
      </div>

      <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
        <div className="bg-white p-6 rounded-xl shadow-lg">
          <h3 className="text-xl font-semibold mb-4 text-gray-800">Recent Sales</h3>
          <div className="space-y-3">
            {sales.slice(-5).map(sale => (
              <div key={sale.id} className="flex justify-between items-center p-3 bg-gray-50 rounded-lg">
                <div>
                  <p className="font-medium">{sale.invoiceNo}</p>
                  <p className="text-sm text-gray-600">{sale.customer?.name}</p>
                </div>
                <span className="font-semibold text-blue-600">{formatCurrency(sale.total)}</span>
              </div>
            ))}
          </div>
        </div>
        
        <div className="bg-white p-6 rounded-xl shadow-lg">
          <h3 className="text-xl font-semibold mb-4 text-gray-800">Low Stock Alert</h3>
          <div className="space-y-3">
            {lowStockProducts.slice(0, 5).map(product => (
              <div key={product.id} className="flex justify-between items-center p-3 bg-red-50 rounded-lg">
                <div>
                  <p className="font-medium">{product.name}</p>
                  <p className="text-sm text-gray-600">{product.category}</p>
                </div>
                <span className="px-3 py-1 bg-red-200 text-red-800 rounded-full text-sm font-medium">
                  {product.stock} {product.unit}
                </span>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  const renderTable = (data, columns, actions) => (
    <div className="overflow-x-auto">
      <table className="w-full bg-white rounded-xl shadow-lg">
        <thead className="bg-gray-50">
          <tr>
            {columns.map((col, index) => (
              <th key={index} className="px-6 py-4 text-left text-sm font-semibold text-gray-600 uppercase tracking-wider">
                {col.header}
              </th>
            ))}
            <th className="px-6 py-4 text-center text-sm font-semibold text-gray-600 uppercase tracking-wider">
              Actions
            </th>
          </tr>
        </thead>
        <tbody className="divide-y divide-gray-200">
          {data.map((item, index) => (
            <tr key={item.id} className="hover:bg-gray-50 transition-colors">
              {columns.map((col, colIndex) => (
                <td key={colIndex} className="px-6 py-4 text-sm text-gray-900">
                  {col.accessor === 'stock' && item.stock <= item.minStock ? (
                    <span className="px-2 py-1 bg-red-100 text-red-800 rounded-full text-xs font-medium">
                      {col.render ? col.render(item[col.accessor], item) : item[col.accessor]}
                    </span>
                  ) : (
                    col.render ? col.render(item[col.accessor], item) : item[col.accessor]
                  )}
                </td>
              ))}
              <td className="px-6 py-4 text-center">
                <div className="flex justify-center space-x-2">
                  {actions.map((action, actionIndex) => (
                    <button
                      key={actionIndex}
                      onClick={() => action.onClick(item)}
                      className={`p-2 rounded-lg transition-colors ${action.className}`}
                      title={action.title}
                    >
                      {action.icon}
                    </button>
                  ))}
                </div>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );

  const renderModal = () => {
    if (!showModal) return null;

    return (
      <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
        <div className="bg-white rounded-xl shadow-2xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
          <div className="p-6 border-b border-gray-200">
            <h3 className="text-2xl font-semibold text-gray-800">
              {editingItem ? 'Edit' : 'Add'} {modalType.charAt(0).toUpperCase() + modalType.slice(1)}
            </h3>
          </div>
          
          <div className="p-6">
            {modalType === 'customer' && (
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                <input
                  type="text"
                  placeholder="Customer Name"
                  value={customerForm.name}
                  onChange={(e) => setCustomerForm({...customerForm, name: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="email"
                  placeholder="Email"
                  value={customerForm.email}
                  onChange={(e) => setCustomerForm({...customerForm, email: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="tel"
                  placeholder="Phone"
                  value={customerForm.phone}
                  onChange={(e) => setCustomerForm({...customerForm, phone: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="text"
                  placeholder="GST Number"
                  value={customerForm.gst}
                  onChange={(e) => setCustomerForm({...customerForm, gst: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <textarea
                  placeholder="Address"
                  value={customerForm.address}
                  onChange={(e) => setCustomerForm({...customerForm, address: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent col-span-2"
                  rows="3"
                />
              </div>
            )}

            {modalType === 'supplier' && (
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                <input
                  type="text"
                  placeholder="Supplier Name"
                  value={supplierForm.name}
                  onChange={(e) => setSupplierForm({...supplierForm, name: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="email"
                  placeholder="Email"
                  value={supplierForm.email}
                  onChange={(e) => setSupplierForm({...supplierForm, email: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="tel"
                  placeholder="Phone"
                  value={supplierForm.phone}
                  onChange={(e) => setSupplierForm({...supplierForm, phone: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="text"
                  placeholder="GST Number"
                  value={supplierForm.gst}
                  onChange={(e) => setSupplierForm({...supplierForm, gst: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <textarea
                  placeholder="Address"
                  value={supplierForm.address}
                  onChange={(e) => setSupplierForm({...supplierForm, address: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent col-span-2"
                  rows="3"
                />
              </div>
            )}

            {modalType === 'product' && (
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                <input
                  type="text"
                  placeholder="Product Name"
                  value={productForm.name}
                  onChange={(e) => setProductForm({...productForm, name: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="text"
                  placeholder="Category"
                  value={productForm.category}
                  onChange={(e) => setProductForm({...productForm, category: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="number"
                  placeholder="Price"
                  value={productForm.price}
                  onChange={(e) => setProductForm({...productForm, price: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="number"
                  placeholder="Stock Quantity"
                  value={productForm.stock}
                  onChange={(e) => setProductForm({...productForm, stock: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="text"
                  placeholder="Unit (pcs, kg, ltr)"
                  value={productForm.unit}
                  onChange={(e) => setProductForm({...productForm, unit: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="number"
                  placeholder="Minimum Stock Level"
                  value={productForm.minStock}
                  onChange={(e) => setProductForm({...productForm, minStock: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
              </div>
            )}

            {modalType === 'sale' && (
              <div className="space-y-6">
                <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                  <select
                    value={saleForm.customerId}
                    onChange={(e) => setSaleForm({...saleForm, customerId: e.target.value})}
                    className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                  >
                    <option value="">Select Customer</option>
                    {customers.map(customer => (
                      <option key={customer.id} value={customer.id}>{customer.name}</option>
                    ))}
                  </select>
                  <input
                    type="date"
                    value={saleForm.date}
                    onChange={(e) => setSaleForm({...saleForm, date: e.target.value})}
                    className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                  />
                </div>

                <div>
                  <div className="flex justify-between items-center mb-4">
                    <h4 className="text-lg font-semibold">Items</h4>
                    <button
                      onClick={() => addItem(saleForm, setSaleForm)}
                      className="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg flex items-center gap-2"
                    >
                      <Plus className="w-4 h-4" />
                      Add Item
                    </button>
                  </div>

                  {saleForm.items.map((item, index) => (
                    <div key={index} className="grid grid-cols-1 md:grid-cols-5 gap-3 mb-3 p-4 bg-gray-50 rounded-lg">
                      <select
                        value={item.productId}
                        onChange={(e) => updateItem(saleForm, setSaleForm, index, 'productId', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      >
                        <option value="">Select Product</option>
                        {products.map(product => (
                          <option key={product.id} value={product.id}>{product.name}</option>
                        ))}
                      </select>
                      <input
                        type="number"
                        placeholder="Quantity"
                        value={item.quantity}
                        onChange={(e) => updateItem(saleForm, setSaleForm, index, 'quantity', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="number"
                        placeholder="Rate"
                        value={item.rate}
                        onChange={(e) => updateItem(saleForm, setSaleForm, index, 'rate', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="number"
                        placeholder="Amount"
                        value={item.amount}
                        readOnly
                        className="p-2 border border-gray-300 rounded bg-gray-100"
                      />
                      <button
                        onClick={() => removeItem(saleForm, setSaleForm, index)}
                        className="bg-red-500 hover:bg-red-600 text-white p-2 rounded flex items-center justify-center"
                      >
                        <Trash2 className="w-4 h-4" />
                      </button>
                    </div>
                  ))}
                </div>

                <div className="grid grid-cols-1 md:grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
                  <div className="space-y-2">
                    <div className="flex justify-between">
                      <span>Subtotal:</span>
                      <span>{formatCurrency(saleForm.subtotal)}</span>
                    </div>
                    <div className="flex justify-between">
                      <span>Tax (18%):</span>
                      <span>{formatCurrency(saleForm.tax)}</span>
                    </div>
                    <div className="flex justify-between font-bold">
                      <span>Total:</span>
                      <span>{formatCurrency(saleForm.total)}</span>
                    </div>
                  </div>
                  <div className="space-y-3">
                    <input
                      type="number"
                      placeholder="Paid Amount"
                      value={saleForm.paidAmount}
                      onChange={(e) => {
                        const paidAmount = e.target.value;
                        const dueAmount = parseFloat(saleForm.total || 0) - parseFloat(paidAmount || 0);
                        setSaleForm({...saleForm, paidAmount, dueAmount: dueAmount.toFixed(2)});
                      }}
                      className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    />
                    <div className="flex justify-between font-semibold">
                      <span>Due Amount:</span>
                      <span className="text-red-600">{formatCurrency(saleForm.dueAmount)}</span>
                    </div>
                  </div>
                </div>
              </div>
            )}

            {modalType === 'purchase' && (
              <div className="space-y-6">
                <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                  <select
                    value={purchaseForm.supplierId}
                    onChange={(e) => setPurchaseForm({...purchaseForm, supplierId: e.target.value})}
                    className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                  >
                    <option value="">Select Supplier</option>
                    {suppliers.map(supplier => (
                      <option key={supplier.id} value={supplier.id}>{supplier.name}</option>
                    ))}
                  </select>
                  <input
                    type="date"
                    value={purchaseForm.date}
                    onChange={(e) => setPurchaseForm({...purchaseForm, date: e.target.value})}
                    className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                  />
                </div>

                <div>
                  <div className="flex justify-between items-center mb-4">
                    <h4 className="text-lg font-semibold">Items</h4>
                    <button
                      onClick={() => addItem(purchaseForm, setPurchaseForm)}
                      className="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg flex items-center gap-2"
                    >
                      <Plus className="w-4 h-4" />
                      Add Item
                    </button>
                  </div>

                  {purchaseForm.items.map((item, index) => (
                    <div key={index} className="grid grid-cols-1 md:grid-cols-5 gap-3 mb-3 p-4 bg-gray-50 rounded-lg">
                      <select
                        value={item.productId}
                        onChange={(e) => updateItem(purchaseForm, setPurchaseForm, index, 'productId', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      >
                        <option value="">Select Product</option>
                        {products.map(product => (
                          <option key={product.id} value={product.id}>{product.name}</option>
                        ))}
                      </select>
                      <input
                        type="number"
                        placeholder="Quantity"
                        value={item.quantity}
                        onChange={(e) => updateItem(purchaseForm, setPurchaseForm, index, 'quantity', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="number"
                        placeholder="Rate"
                        value={item.rate}
                        onChange={(e) => updateItem(purchaseForm, setPurchaseForm, index, 'rate', e.target.value)}
                        className="p-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="number"
                        placeholder="Amount"
                        value={item.amount}
                        readOnly
                        className="p-2 border border-gray-300 rounded bg-gray-100"
                      />
                      <button
                        onClick={() => removeItem(purchaseForm, setPurchaseForm, index)}
                        className="bg-red-500 hover:bg-red-600 text-white p-2 rounded flex items-center justify-center"
                      >
                        <Trash2 className="w-4 h-4" />
                      </button>
                    </div>
                  ))}
                </div>

                <div className="grid grid-cols-1 md:grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
                  <div className="space-y-2">
                    <div className="flex justify-between">
                      <span>Subtotal:</span>
                      <span>{formatCurrency(purchaseForm.subtotal)}</span>
                    </div>
                    <div className="flex justify-between">
                      <span>Tax (18%):</span>
                      <span>{formatCurrency(purchaseForm.tax)}</span>
                    </div>
                    <div className="flex justify-between font-bold">
                      <span>Total:</span>
                      <span>{formatCurrency(purchaseForm.total)}</span>
                    </div>
                  </div>
                  <div className="space-y-3">
                    <input
                      type="number"
                      placeholder="Paid Amount"
                      value={purchaseForm.paidAmount}
                      onChange={(e) => {
                        const paidAmount = e.target.value;
                        const dueAmount = parseFloat(purchaseForm.total || 0) - parseFloat(paidAmount || 0);
                        setPurchaseForm({...purchaseForm, paidAmount, dueAmount: dueAmount.toFixed(2)});
                      }}
                      className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    />
                    <div className="flex justify-between font-semibold">
                      <span>Due Amount:</span>
                      <span className="text-red-600">{formatCurrency(purchaseForm.dueAmount)}</span>
                    </div>
                  </div>
                </div>
              </div>
            )}

            {modalType === 'payment' && (
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                <select
                  value={paymentForm.type}
                  onChange={(e) => setPaymentForm({...paymentForm, type: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                >
                  <option value="payment">Payment (to Supplier)</option>
                  <option value="receipt">Receipt (from Customer)</option>
                </select>
                <select
                  value={paymentForm.entityType}
                  onChange={(e) => setPaymentForm({...paymentForm, entityType: e.target.value, entityId: ''})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                >
                  <option value="customer">Customer</option>
                  <option value="supplier">Supplier</option>
                </select>
                <select
                  value={paymentForm.entityId}
                  onChange={(e) => setPaymentForm({...paymentForm, entityId: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                >
                  <option value="">Select {paymentForm.entityType}</option>
                  {(paymentForm.entityType === 'customer' ? customers : suppliers).map(entity => (
                    <option key={entity.id} value={entity.id}>{entity.name}</option>
                  ))}
                </select>
                <input
                  type="number"
                  placeholder="Amount"
                  value={paymentForm.amount}
                  onChange={(e) => setPaymentForm({...paymentForm, amount: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <input
                  type="date"
                  value={paymentForm.date}
                  onChange={(e) => setPaymentForm({...paymentForm, date: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                />
                <select
                  value={paymentForm.method}
                  onChange={(e) => setPaymentForm({...paymentForm, method: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                >
                  <option value="cash">Cash</option>
                  <option value="cheque">Cheque</option>
                  <option value="bank">Bank Transfer</option>
                  <option value="card">Card</option>
                </select>
                <input
                  type="text"
                  placeholder="Reference"
                  value={paymentForm.reference}
                  onChange={(e) => setPaymentForm({...paymentForm, reference: e.target.value})}
                  className="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent col-span-2"
                />
              </div>
            )}
          </div>
          
          <div className="p-6 border-t border-gray-200 flex justify-end space-x-4">
            <button
              onClick={closeModal}
              className="px-6 py-3 bg-gray-300 hover:bg-gray-400 text-gray-700 rounded-lg font-medium transition-colors"
            >
              Cancel
            </button>
            <button
              onClick={() => {
                if (modalType === 'customer') handleSaveCustomer();
                else if (modalType === 'supplier') handleSaveSupplier();
                else if (modalType === 'product') handleSaveProduct();
                else if (modalType === 'sale') handleSaveSale();
                else if (modalType === 'purchase') handleSavePurchase();
                else if (modalType === 'payment') handleSavePayment();
              }}
              className="px-6 py-3 bg-blue-500 hover:bg-blue-600 text-white rounded-lg font-medium transition-colors"
            >
              {editingItem ? 'Update' : 'Save'}
            </button>
          </div>
        </div>
      </div>
    );
  };

  const tabs = [
    { id: 'dashboard', name: 'Dashboard', icon: TrendingUp },
    { id: 'customers', name: 'Customers', icon: Users },
    { id: 'suppliers', name: 'Suppliers', icon: Building2 },
    { id: 'products', name: 'Products', icon: Package },
    { id: 'sales', name: 'Sales', icon: FileText },
    { id: 'purchases', name: 'Purchases', icon: ShoppingCart },
    { id: 'payments', name: 'Payments', icon: CreditCard }
  ];

  return (
    <div className="min-h-screen bg-gray-100">
      {/* Header */}
      <div className="bg-white shadow-sm border-b">
        <div className="px-6 py-4">
          <h1 className="text-2xl font-bold text-gray-800">Sales & Purchase Management</h1>
        </div>
      </div>

      {/* Navigation */}
      <div className="bg-white shadow-sm">
        <div className="px-6">
          <nav className="flex space-x-8">
            {tabs.map((tab) => {
              const Icon = tab.icon;
              return (
                <button
                  key={tab.id}
                  onClick={() => setActiveTab(tab.id)}
                  className={`flex items-center space-x-2 py-4 px-2 border-b-2 font-medium text-sm transition-colors ${
                    activeTab === tab.id
                      ? 'border-blue-500 text-blue-600'
                      : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'
                  }`}
                >
                  <Icon className="w-4 h-4" />
                  <span>{tab.name}</span>
                </button>
              );
            })}
          </nav>
        </div>
      </div>

      {/* Content */}
      <div className="p-6">
        {activeTab === 'dashboard' && renderDashboard()}

        {activeTab === 'customers' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Customers</h2>
              <button
                onClick={() => openModal('customer')}
                className="bg-blue-500 hover:bg-blue-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                Add Customer
              </button>
            </div>
            {renderTable(
              customers,
              [
                { header: 'Name', accessor: 'name' },
                { header: 'Email', accessor: 'email' },
                { header: 'Phone', accessor: 'phone' },
                { header: 'GST', accessor: 'gst' }
              ],
              [
                {
                  icon: <Edit className="w-4 h-4" />,
                  onClick: (item) => openModal('customer', item),
                  className: 'bg-blue-100 hover:bg-blue-200 text-blue-600',
                  title: 'Edit'
                }
              ]
            )}
          </div>
        )}

        {activeTab === 'suppliers' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Suppliers</h2>
              <button
                onClick={() => openModal('supplier')}
                className="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                Add Supplier
              </button>
            </div>
            {renderTable(
              suppliers,
              [
                { header: 'Name', accessor: 'name' },
                { header: 'Email', accessor: 'email' },
                { header: 'Phone', accessor: 'phone' },
                { header: 'GST', accessor: 'gst' }
              ],
              [
                {
                  icon: <Edit className="w-4 h-4" />,
                  onClick: (item) => openModal('supplier', item),
                  className: 'bg-green-100 hover:bg-green-200 text-green-600',
                  title: 'Edit'
                }
              ]
            )}
          </div>
        )}

        {activeTab === 'products' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Products</h2>
              <button
                onClick={() => openModal('product')}
                className="bg-purple-500 hover:bg-purple-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                Add Product
              </button>
            </div>
            {renderTable(
              products,
              [
                { header: 'Name', accessor: 'name' },
                { header: 'Category', accessor: 'category' },
                { header: 'Price', accessor: 'price', render: (value) => formatCurrency(value) },
                { header: 'Stock', accessor: 'stock', render: (value, item) => `${value} ${item.unit}` },
                { header: 'Min Stock', accessor: 'minStock', render: (value, item) => `${value} ${item.unit}` }
              ],
              [
                {
                  icon: <Edit className="w-4 h-4" />,
                  onClick: (item) => openModal('product', item),
                  className: 'bg-purple-100 hover:bg-purple-200 text-purple-600',
                  title: 'Edit'
                }
              ]
            )}
          </div>
        )}

        {activeTab === 'sales' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Sales</h2>
              <button
                onClick={() => openModal('sale')}
                className="bg-blue-500 hover:bg-blue-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                New Sale
              </button>
            </div>
            {renderTable(
              sales,
              [
                { header: 'Invoice No', accessor: 'invoiceNo' },
                { header: 'Customer', accessor: 'customer', render: (value) => value?.name || '-' },
                { header: 'Date', accessor: 'date' },
                { header: 'Total', accessor: 'total', render: (value) => formatCurrency(value) },
                { header: 'Due', accessor: 'dueAmount', render: (value) => formatCurrency(value) }
              ],
              [
                {
                  icon: <Eye className="w-4 h-4" />,
                  onClick: (item) => console.log('View sale:', item),
                  className: 'bg-gray-100 hover:bg-gray-200 text-gray-600',
                  title: 'View'
                }
              ]
            )}
          </div>
        )}

        {activeTab === 'purchases' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Purchases</h2>
              <button
                onClick={() => openModal('purchase')}
                className="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                New Purchase
              </button>
            </div>
            {renderTable(
              purchases,
              [
                { header: 'Bill No', accessor: 'billNo' },
                { header: 'Supplier', accessor: 'supplier', render: (value) => value?.name || '-' },
                { header: 'Date', accessor: 'date' },
                { header: 'Total', accessor: 'total', render: (value) => formatCurrency(value) },
                { header: 'Due', accessor: 'dueAmount', render: (value) => formatCurrency(value) }
              ],
              [
                {
                  icon: <Eye className="w-4 h-4" />,
                  onClick: (item) => console.log('View purchase:', item),
                  className: 'bg-gray-100 hover:bg-gray-200 text-gray-600',
                  title: 'View'
                }
              ]
            )}
          </div>
        )}

        {activeTab === 'payments' && (
          <div>
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-3xl font-bold text-gray-800">Payments & Receipts</h2>
              <button
                onClick={() => openModal('payment')}
                className="bg-yellow-500 hover:bg-yellow-600 text-white px-6 py-3 rounded-lg flex items-center gap-2 font-medium"
              >
                <Plus className="w-5 h-5" />
                Add Transaction
              </button>
            </div>
            
            <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
              <div className="bg-white p-6 rounded-xl shadow-lg">
                <h3 className="text-xl font-semibold mb-4 text-gray-800">Recent Payments</h3>
                <div className="space-y-3">
                  {payments.slice(-5).map(payment => (
                    <div key={payment.id} className="flex justify-between items-center p-3 bg-red-50 rounded-lg">
                      <div>
                        <p className="font-medium">{payment.entity?.name}</p>
                        <p className="text-sm text-gray-600">{payment.method} • {payment.date}</p>
                      </div>
                      <span className="font-semibold text-red-600">-{formatCurrency(payment.amount)}</span>
                    </div>
                  ))}
                </div>
              </div>
              
              <div className="bg-white p-6 rounded-xl shadow-lg">
                <h3 className="text-xl font-semibold mb-4 text-gray-800">Recent Receipts</h3>
                <div className="space-y-3">
                  {receipts.slice(-5).map(receipt => (
                    <div key={receipt.id} className="flex justify-between items-center p-3 bg-green-50 rounded-lg">
                      <div>
                        <p className="font-medium">{receipt.entity?.name}</p>
                        <p className="text-sm text-gray-600">{receipt.method} • {receipt.date}</p>
                      </div>
                      <span className="font-semibold text-green-600">+{formatCurrency(receipt.amount)}</span>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}
      </div>

      {renderModal()}
    </div>
  );
};

export default SalesPurchaseApp;
