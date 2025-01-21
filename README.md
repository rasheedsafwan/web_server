# Multi-Client Web Server

This project demonstrates the implementation of a Java-based server capable of handling multiple client connections. It includes three approaches for managing client requests: Single-Threaded, Multi-Threaded, and Thread-Pool-Based servers. Each implementation is designed to address specific workloads and scalability requirements.

---

## Features

1. **Single-Threaded Server**:
   - Handles one client connection at a time.
   - Simple and suitable for low-traffic scenarios.

2. **Multi-Threaded Server**:
   - Spawns a new thread for each client connection.
   - Enables concurrent client handling but may lead to high resource usage under heavy load.

3. **Thread-Pool-Based Server**:
   - Utilizes a fixed-size thread pool to manage client connections.
   - Ensures efficient resource usage and scalability for high-traffic environments.

---

## Technologies Used

- **Java**: Core language for implementing server logic.
- **Sockets (TCP/IP)**: For handling client-server communication.
- **Multithreading**: To enable concurrent client processing.
- **ExecutorService**: For thread pool management in the Thread-Pool server.

---

## Threading Models Explained

1. **Single-Threaded Server**:
   - **How it works**: One thread handles all incoming client connections and processes them sequentially.
   - **Advantages**:
     - Simple to implement.
     - Minimal resource usage.
   - **Disadvantages**:
     - Cannot handle multiple clients simultaneously.
     - Performance bottleneck for applications with high traffic.

2. **Multi-Threaded Server**:
   - **How it works**: Creates a new thread for each client connection. Each thread independently processes the client request.
   - **Advantages**:
     - Enables concurrent handling of multiple clients.
     - Suitable for moderate workloads.
   - **Disadvantages**:
     - High resource usage due to the overhead of creating and managing threads.
     - Poor scalability under heavy traffic.

3. **Thread-Pool-Based Server**:
   - **How it works**: Uses a fixed-size thread pool where threads are reused to process client connections.
   - **Advantages**:
     - Efficient resource management by limiting the number of threads.
     - Scalable and suitable for high-traffic applications.
   - **Disadvantages**:
     - Requires careful tuning of the thread pool size to balance performance and resource usage.

---

## How It Works

### Thread-Pool Server Implementation

1. **Server Initialization**:
   - A `ServerSocket` listens on a specified port (default: `8010`).
   - A fixed-size thread pool is created using `ExecutorService`.

2. **Client Handling**:
   - The server accepts incoming client connections.
   - Each client is assigned to a thread in the thread pool.
   - The `handleClient` method processes the client request and sends a response.

3. **Graceful Shutdown**:
   - Ensures proper shutdown of threads and resource cleanup.

---

## How to Run

1. **Clone the Repository**:
   ```bash
   git clone <repository_url>
   cd web_server
   ```

2. **Compile and Run**:
   - Compile:
     ```bash
     javac Server.java
     ```
   - Run:
     ```bash
     java Server
     ```

3. **Connect a Client**:
   - Use a client tool like `telnet` or a custom client to connect:
     ```bash
     telnet localhost 8010
     ```
   - The server will respond with a welcome message.

---

## Future Enhancements

- Add support for secure connections (SSL/TLS).
- Implement advanced client handling (e.g., file uploads/downloads).
- Add logging for better debugging and monitoring.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

For any questions or feedback, please contact **[Rasheed Safwan](mailto:rasheedsafwan23@gmail.com)**.
