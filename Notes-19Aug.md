## OSI MODEL-OPEN SYSTEM INTERCONNECTION

Developed by the International Organization for Standardization `(ISO)` in 1984, it divides the communication process into seven distinct layers.
Each layer has specific functions and interacts with the layers directly above and below it. This model helps in troubleshooting, designing, and understanding network protocols and services.



### 1. Physical Layer 🛠️

- **Function**: Handles the physical connection between devices (cables, switches).
- `Example` Ethernet cables, Wi-Fi signals.
- **Advantages**:
  - **Direct Communication**: Enables direct hardware communication.
  - **Speed**: High-speed data transfer.
- **Disadvantages**:
  - **Limited Scope**: Only deals with physical aspects.
  - **Vulnerability**: Susceptible to physical damage and interference.

### 2. Data Link Layer 🔗
- **Function**: Ensures data transfer between devices on the same network.
- `Example` MAC addresses, switches.
- **Advantages**:
  - **Error Detection**: Identifies and corrects errors in data frames.
  - **Flow Control**: Manages data flow to prevent congestion.
- **Disadvantages**:
  - **Limited to Local Network**: Only works within a single network.
  - **Complexity**: Can be complex due to error handling mechanisms.

### 3. Network Layer 🌐

Data comes into packet form 
- **Function**: Manages data routing between different networks.
- `Example` IP addresses, routers.
- **Advantages**:
  - **Routing**: Efficiently routes data across networks.
  - **Scalability**: Supports large and complex networks.
- **Disadvantages**:
  - **Congestion**: Can suffer from network congestion.
  - **Security**: Vulnerable to routing attacks.

### 4. Transport Layer 🚚
- **Function**: Ensures complete data transfer with error checking & flow control.
- `Example` TCP, UDP.
- **Advantages**:
  - **Reliability**: Guarantees data delivery.
  - **Error Recovery**: Handles data retransmission if errors occur.
- **Disadvantages**:
  - **Overhead**: Adds extra data for error checking.
  - **Latency**: Can introduce delays due to error correction.

### 5. Session Layer 🗂️
- **Function**: Manages sessions or connections between applications.
- `Example`  Logging in and out of a website.
- **Advantages**:
  - **Session Management**: Keeps track of sessions.
  - **Synchronization**: Ensures data is properly synchronized.
- **Disadvantages**:
  - **Overhead**: Adds extra data for session management.
  - **Complexity**: Can be complex to implement.

### 6. Presentation Layer 🎨
- **Function**: Translates data between the application layer and the network.
- 
- `Example` Encryption, data compression.

- **Advantages**:
  - **Data Translation**: Converts data formats.
  - **Encryption**: Provides data encryption for security.
- **Disadvantages**:
  - **Processing Time**: Can slow down data processing.
  - **Compatibility Issues**: May face compatibility problems with different data formats.

### 7. Application Layer 📱
- **Function**: Provides network services directly to user applications.
- `Example` Web browsers, email clients.
- **Advantages**:
  - **User Interaction**: Directly interacts with user applications.
  - **Service Provision**: Offers various network services.
- **Disadvantages**:
  - **Security Risks**: Vulnerable to application-level attacks.
  - **Resource Intensive**: Can consume significant system resources.
