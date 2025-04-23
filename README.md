A tool for analyzing CPU information using the CPUID instruction. <br>
It collects and outputs detailed information about the processor and its caches directly to the console.<br>
I Plan to add Gui with ImGui or QT. <br>

Used: CPUID instruction, x86/x64 architecture, libcpuid, OpenHardwareMonitor<br>

Challenges:<br>
1. The CPUID instruction works directly with CPU registers, so to interpret its output, I had to study binary logic and CPU architecture.<br>
My initial idea was to parse Intel’s documentation into a MySQL database using a Python script, and then match that data against live CPUID results in C++ via MySQL queries.<br>
Later, I discovered the libcpuid library, which significantly simplified the decoding process.<br><br>
2.On Windows, accessing advanced CPU metrics (such as voltage and clock speeds) requires kernel-mode access.<br>
Since modern Windows versions block unsigned drivers unless secure boot is disabled—a serious security risk—I decided not to bypass this restriction and paused development at that point.<br>
