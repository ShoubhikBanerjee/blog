---
title: "Milvus Node.js SDK 3.0.5 adds telemetry and Bloom filters"
slug: "milvus-node-js-sdk-3-0-5-adds-telemetry-and-bloom-filters"
description: "The official Node.js SDK for the Milvus vector database has released version 3.0.5. This update introduces Bloom and Roaring membership helpers, enables client telemetry by default, and adds six..."
date: 2026-11-17T18:10:30+05:30
tags: [Milvus, NodeJS, VectorDatabase, SDK, zilliz]
categories: ["AI", "Vector Databases", "Developer Tools", "Data Infrastructure", "Software Development"]
image: "https://avatars.githubusercontent.com/u/51735404?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Milvus Node.js SDK 3.0.5 adds telemetry and Bloom filters

The official Node.js SDK for the Milvus vector database has released version 3.0.5. This update introduces Bloom and Roaring membership helpers, enables client telemetry by default, and adds six additional index enum values.

## 📦 Installation and Connection

Developers can install the SDK using standard package managers:

```bash
npm install @zilliz/milvus2-sdk-node
# or
yarn add @zilliz/milvus2-sdk-node
```

The SDK supports gRPC and HTTP clients for vector similarity search, metadata filtering, and collection management. Users can initialize the `MilvusClient` with various authentication and connection parameters:

```javascript
import { MilvusClient } from '@zilliz/milvus2-sdk-node';

const client = new MilvusClient({
  address: 'localhost:19530',
  username: 'root',
  password: 'milvus',
});

await client.connectPromise;
```

Configuration options include SSL/TLS settings, database selection, request timeouts, retry policies, and connection pooling. The `telemetry` option is enabled by default, and `trace` can enable OpenTelemetry tracing.

## ⚙️ Collection Management and Data Types

The SDK facilitates the creation of collections with specific field types and index parameters. Recent versions (3.0.4) added support for `Text` fields and asynchronous function-field backfill.

```javascript
await client.createCollection({
  collection_name: 'my_collection',
  fields: [
    {
      name: 'id',
      data_type: DataType.Int64,
      is_primary_key: true,
      autoID: true,
    },
    { name: 'text', data_type: DataType.VarChar, max_length: 512 },
    { name: 'vector', data_type: DataType.FloatVector, dim: 128 },
  ],
  index_params: [
    {
      field_name: 'vector',
      index_type: 'HNSW',
      metric_type: MetricType.COSINE,
      params: { M: 16, efConstruction: 256 },
    },
  ],
  enable_dynamic_field: true,
});
```

## 🔍 Search and Insertion

The SDK allows for synchronous collection loading and data insertion. The `search` method supports specifying a consistency level to include recently inserted rows.

```javascript
await client.loadCollectionSync({ collection_name: 'my_collection' });

await client.insert({
  collection_name: 'my_collection',
  data: [
    { vector: Array(128).fill(0.1), text: 'doc1' },
    { vector: Array(128).fill(0.2), text: 'doc2' },
  ],
});

const results = await client.search({
  collection_name: 'my_collection',
  data: [Array(128).fill(0.1)],
  limit: 10,
  consistency_level: 'Strong',
  output_fields: ['text'],
});
```

## 🧩 API Capabilities

The SDK exposes a range of enums and utilities for precise control:

*   **DataType**: Includes `Int64`, `VarChar`, `FloatVector`, and `Text`.
*   **MetricType**: Includes `COSINE`.
*   **IndexType**: Includes `HNSW`.
*   **ConsistencyLevelEnum**: Includes `Strong`.
*   **Utilities**: `BulkWriter` is available for bulk operations.

The `upsert` method supports partial updates and specific field operations, while `insert` accepts an array of row objects for partitioned data.

#Milvus #NodeJS #VectorDatabase #SDK #zilliz

---

*Source: [milvus-io/milvus-sdk-node](https://github.com/milvus-io/milvus-sdk-node)*
