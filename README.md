A tool for analyzing CPU information using the CPUID instruction. <br>
It collects and outputs detailed information about the processor and its caches directly to the console.<br>
Plan to add Gui with ImGui. <br>

Used: CPUID instruction, x86/x64 architecture, libcpuid, OpenHardwareMonitor<br>

Challenges:<br>
 1. I had to use the CPUID instruction, which works directly with CPU registers. <br>
 To interpret the output, I studied binary operations and logic, and consulted Intel’s official documentation. <br>
 Later, I discovered the libcpuid library, which significantly simplified data decoding.<br><br>
 2. Windows user-mode restrictions: To access advanced CPU metrics such as voltage and clock speeds, kernel-mode access was required. <br>
 However, unsigned drivers are blocked on modern Windows systems unless secure boot features are disabled — a security risk I chose to avoid. <br>
 As a result, I paused development at that point.<br>
