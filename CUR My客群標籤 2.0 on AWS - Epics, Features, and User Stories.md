<h1 id="toc_0">CUR My客群標籤 2.0 on AWS - Epics, Features, and User Stories</h1>

<h2 id="toc_1">Epic 1: Data Ingestion and Preparation:</h2>

<h3 id="toc_2">Feature 1: Data Ingestion</h3>

<h4 id="toc_3">User Story 1:</h4>

<p>As a Data Engineer, I want to set up a data ingestion pipeline from on-premises to AWS S3, so that I can efficiently transfer data to the cloud.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_4">User Story 2:</h4>

<p>As a Data Engineer, I want to implement secure data transfer mechanisms, so that sensitive data remains protected during the transfer.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_5">User Story 3:</h4>

<p>As a Data Engineer, I want to schedule periodic data ingestion jobs, so that data is regularly updated in the AWS S3 storage. </p>

##### Acceptance Criteria:
- 

<h3 id="toc_6">Feature 2: Data Transformation and Encryption</h3>

<h4 id="toc_7">User Story 1:</h4>

<p>As a Data Engineer, I want to develop Glue ETL jobs for data transformation, so that I can preprocess the data for further processing.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_8">User Story 2:</h4>

<p>As a Data Engineer, I want to implement data masking or data encryption algorithms, so that sensitive information remains confidential.</p>

##### Acceptance Criteria:
- DE, DA, DS, DM, AP 不可以看到明碼的產出結果
- DE 開發過程中任何服務也不能看到明碼
- 確認資料 加密/masking 處理的效能(待國泰同仁提供數據以及加密程式)
- 確認 加密/masking 產出結果是否與預期一致

<h4 id="toc_9">User Story 3:</h4>

<p>As a Data Engineer, I want to ensure data integrity during transformation, so that accurate and reliable data is available for analysis. </p>

##### Acceptance Criteria:
- 確認資料 加密/masking 處理的效能(待國泰同仁提供數據以及加密程式)
- 確認 加密/masking 產出結果是否與預期一致
- System Account 可以看到明碼

<h2 id="toc_10">Epic 2: Data Transformation and Aggregation:</h2>

<h3 id="toc_11">Feature 1: Data Transformation</h3>

<h4 id="toc_12">User Story 1:</h4>

<p>As a Data Engineer, I want to build Glue ETL scripts for data transformation, so that I can efficiently transform the data from the Raw Layer.</p>

##### Acceptance Criteria:
- DRV table 如期沒有錯誤產生符合預期的執行與產生
- DE, DA, DS, DM, AP 不可以看到明碼的產出結果
- DE 開發過程中任何服務也不能看到明碼
- System Account 可以看到明碼

<h4 id="toc_13">User Story 2:</h4>

<p>As a Data Engineer, I want to handle data format conversions and cleanup, so that the transformed data is consistent and ready for aggregation. </p>

##### Acceptance Criteria:
- 

<h4 >User Story 3:</h4>

<p>As a Data Engineer, I want to integrate MWAA and DataHub, so that the Data Manager can manage and trace the data lineage. </p>

##### Acceptance Criteria:
- DM 可以在 DataHub中發現最新的狀況與正確的 Data lineage結果

<h4 >User Story 4:</h4>

<p>As a Data Engineer, I want to develop DAG on the MWAA to manage ETL jobs, so that I can verify the job status </p>

##### Acceptance Criteria:
- MWAA 可以正常監控
- Error 發生時是否可以正常發現與處理 

<h3 id="toc_14">Feature 2: Aggregation and Storage</h3>


<h4 id="toc_16">User Story 1:</h4>

<p>As a Data Manager, I want to design a storage structure in the every Layer, so that aggregated data is organized and easily accessible. </p>

##### Acceptance Criteria:
- DataHub中可以看到對應的Zone與預期的表
- Every layer 包含Raw Layer, Transformed Layer, Consumption Layer, Data Mart

<h2 id="toc_17">Epic 3: Data Processing and Modeling:</h2>

<h3 id="toc_18">Feature 1: Data Processing</h3>

<h4 id="toc_19">User Story 1:</h4>

<p>As a Data Scientist, I want to implement data cleaning and preprocessing, so that the data is of high quality and ready for analysis.</p>

##### Acceptance Criteria:
- 使用 PySpark 連線 EMR 可以正確的查詢資裡，並且是暗碼
- 查詢的資料皆只能是暗碼
- 透過 Redshift Spectrum可以拿到資料，並且是暗碼 


<h3 id="toc_21">Feature 2: Machine Learning Modeling</h3>

<h4 id="toc_22">User Story 1:</h4>

<p>As a Data Scientist, I want to create SageMaker jobs for model training, so that I can develop accurate machine learning models.</p>

##### Acceptance Criteria:
- 確認 modeling 過程中是否狀態正常


<h2 id="toc_24">Epic 4: Model Post-Processing and Data Quality Check:</h2>

<h3 id="toc_25">Feature 1: Model History Processing</h3>

<h4 id="toc_26">User Story 1:</h4>

<p>As a Data Scientist, I want to develop SparkSQL queries for historical analysis, so that I can analyze model performance over time.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_27">User Story 2:</h4>

<p>As a Data Scientist, I want to design scripts to track model changes over time, so that model versioning is well-maintained. </p>

##### Acceptance Criteria:
- 

<h3 id="toc_28">Feature 2: Data Quality Check and Validation</h3>

<h4 id="toc_29">User Story 1:</h4>

<p>As a Data Scientist, I want to implement Glue Data Quality checks, so that I can ensure data quality before further processing.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_30">User Story 2:</h4>

<p>As a Data Scientist, I want to set up SNS notifications for data quality issues, so that I can promptly address any data quality concerns. </p>

##### Acceptance Criteria:
- 

<h2 id="toc_31">Epic 5: Data Retrieval and Storage:</h2>

<h3 id="toc_32">Feature 1: Data Retrieval</h3>

<h4 id="toc_33">User Story 1:</h4>

<p>As an Application Developer, I want to design Lambda functions for data retrieval from Data Consumption Layer, so that I can efficiently access data for applications.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_15">User Story 2:</h4>

<p>As a Data Analyst, I want to develop aggregation algorithms for different metrics, so that I can analyze data trends effectively.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_34">User Story 3:</h4>

<p>As an Application Developer, I want to ensure efficient querying and data extraction, so that application users experience responsive data retrieval.</p>

##### Acceptance Criteria:
- 

<h3 id="toc_35">Feature 2: Data Storage and Replication</h3>

<h4 id="toc_36">User Story 1:</h4>

<p>As a Application Developer, I want to develop mechanisms to store data in RDS Oracle, so that data is reliably stored for long-term use.</p>

##### Acceptance Criteria:
- 

<h4 id="toc_37">User Story 2:</h4>

<p>As a Application Developer, I want to implement data replication between Data Consumption Layer and RDS Oracle, so that data consistency is maintained across different storage solutions.</p>

##### Acceptance Criteria:
- 

<h2 id="toc_38">Epic 6: Data Management and Data Governance:</h2>

<h3 id="toc_39">Feature 1: DataHub Integration</h3>

<h4 id="toc_40">User Story1:</h4>

<p>As a Data Manager, I want to collaborate with Data Engineers to integrate DataHub into all MWAA workflows, so that we can capture comprehensive data lineage information.</p>

##### Acceptance Criteria:
- 

<h3 id="toc_41">Feature 2: Lake Formation Permissions Setup</h3>

<h4 id="toc_42">User Story 1:</h4>

<p>As a Data Manager, I want to configure Lake Formation for controlling permissions, so that all processes have controlled access to data resources.</p>

<h3 id="toc_43">Feature 3: Data Catalog Integration for Glue Data Sources</h3>

##### Acceptance Criteria:
- 

<h4 id="toc_44">User Story 1:</h4>

<p>As a Data Manager, I want to ensure that all Glue Data Sources are registered in the Data Catalog,so that they are well-organized and easily accessible.</p>

##### Acceptance Criteria:
- 
