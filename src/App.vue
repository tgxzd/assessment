<script setup lang="ts">
// Table 1 data from the provided image
const table1Data = [
  { index: 'A1', value: 41 },
  { index: 'A2', value: 18 },
  { index: 'A3', value: 21 },
  { index: 'A4', value: 61 },
  { index: 'A5', value: 2 },
  { index: 'A6', value: 53 },
  { index: 'A7', value: 5 },
  { index: 'A8', value: 57 },
  { index: 'A9', value: 60 },
  { index: 'A10', value: 93 },
  { index: 'A11', value: 28 },
  { index: 'A12', value: 3 },
  { index: 'A13', value: 90 },
  { index: 'A14', value: 39 },
  { index: 'A15', value: 80 },
  { index: 'A16', value: 46 },
  { index: 'A17', value: 49 },
  { index: 'A18', value: 60 },
  { index: 'A19', value: 28 },
  { index: 'A20', value: 26 }
];

// Create a lookup object for easy access
const dataLookup = table1Data.reduce((acc, item) => {
  acc[item.index] = item.value;
  return acc;
}, {} as Record<string, number>);

// Calculate Table 2 values
const table2Data = [
  { 
    category: 'Alpha', 
    value: dataLookup['A5'] + dataLookup['A20'] // 2 + 26 = 28
  },
  { 
    category: 'Beta', 
    value: dataLookup['A15'] / dataLookup['A7'] // 80 / 5 = 16
  },
  { 
    category: 'Charlie', 
    value: dataLookup['A13'] * dataLookup['A12'] // 90 * 3 = 270
  }
];
</script>

<template>
  <div class="app-container">
    <h1>Internship Assessment - Table Output & Processing</h1>
    
    <!-- Table 1 -->
    <div class="table-section">
      <h2>Table 1</h2>
      <table class="data-table">
        <thead>
          <tr>
            <th>Index #</th>
            <th>Value</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in table1Data" :key="item.index">
            <td>{{ item.index }}</td>
            <td>{{ item.value }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Table 2 -->
    <div class="table-section">
      <h2>Table 2</h2>
      <table class="data-table">
        <thead>
          <tr>
            <th>Category</th>
            <th>Value</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in table2Data" :key="item.category">
            <td>{{ item.category }}</td>
            <td>{{ item.value }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style scoped>
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

h1 {
  text-align: center;
  color: #333;
  margin-bottom: 30px;
}

h2 {
  color: #555;
  margin-bottom: 15px;
}

.table-section {
  margin-bottom: 40px;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  border-radius: 8px;
  overflow: hidden;
}

.data-table th,
.data-table td {
  border: 1px solid #e0e7ff;
  padding: 14px 16px;
  text-align: left;
}

.data-table th {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  font-weight: bold;
  color: white;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
  font-size: 14px;
  letter-spacing: 0.5px;
}

.data-table td {
  background-color: white;
  color: #2d3748;
  font-weight: 500;
}

.data-table tr:nth-child(even) td {
  background-color: #f8fafc;
}

.data-table tr:hover td {
  background-color: #e6fffa;
  transform: scale(1.01);
  transition: all 0.2s ease;
}
</style>
