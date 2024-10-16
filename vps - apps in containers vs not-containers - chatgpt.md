If the **same application** is running in **identical environments**, but one instance is containerized while the other is not, the **non-containerized** version is likely to be more performant. However, the difference in performance might be small and depends on various factors.

### Reasons why the non-containerized application might be more performant:

1. **Overhead of Containerization**:
   - **Containers** introduce a small amount of overhead because of the extra layer between the application and the host system. This layer includes the container runtime (e.g., Docker) and additional abstractions such as namespaces, cgroups, and virtual networking.
   - The **non-containerized** version runs directly on the host's operating system, avoiding this overhead.

2. **System Resource Utilization**:
   - **Non-containerized applications** can directly access system resources (e.g., CPU, memory, storage) without going through the container runtime or additional abstraction layers.
   - In contrast, **containerized applications** may face some delays due to container orchestration or runtime processing (though in most cases, the overhead is minimal).

3. **Network Performance**:
   - Networking for **containerized applications** often involves virtual interfaces and bridge networks, which can add minor latency and complexity.
   - **Non-containerized applications** can access network interfaces directly, potentially resulting in lower network latency.

### When the performance difference might be negligible:

1. **Modern Container Engines**:
   - Tools like Docker and Kubernetes are optimized to minimize the overhead they introduce. In many cases, the performance gap is small, and containerized applications can perform similarly to non-containerized ones.

2. **Same OS Kernel**:
   - Containers share the same OS kernel with the host system, so the performance difference is usually minimal compared to full virtualization. This makes the performance of containerized applications quite close to those running directly on the host.

3. **Application Type**:
   - Some applications, especially those that are **I/O-bound** or perform **network-intensive** tasks, may not experience a noticeable difference in performance between containerized and non-containerized environments.

### Key Takeaways:
- In theory, the **non-containerized application** will be **slightly more performant** due to the lack of container runtime overhead.
- In practice, the difference is often small and may be outweighed by the benefits of using containers, such as portability, scalability, and easier deployment.
  
If performance is critical and you are measuring at very fine margins, non-containerized could edge out, but for most applications, the benefits of containers outweigh the minor performance trade-offs.