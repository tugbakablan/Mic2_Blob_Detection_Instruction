# Mic-2 Custom Instruction for Blob Detection

<img width="490" height="310" alt="image" src="https://github.com/user-attachments/assets/fdccfb76-a623-4d78-aec8-f906982f0f47" />

This project includes the design of a custom instruction on the Mic-2
microprogrammed processor architecture. The instruction performs
color-based blob detection on image data stored in D-Cache memory.

The project was developed as part of the BIM 327 Computer Architecture course.

## Contents:
- Project report - time analysis & architecture diagrams
- Microcode steps

## Result

In the worst-case scenario, when the blob is located at the last pixel of the image, the total number of micro-operations is calculated as follows:

Initialization stage: 5 micro-operations
Pixel scanning loop:
 65,536 pixels × 6 micro-operations = 393,216 micro-operations
Coordinate calculation: 4 micro-operations

Total number of micro-operations: 5 + 393,216 + 4 = 393,225 micro-operations

Given that each micro-operation takes 1 ns, the total execution time of the custom instruction is:
393,225 ns → 0.393 ms

## Real-Time System Evaluation
The system operates at 120 frames per second (FPS), so the maximum allowable time per frame is approximately 8.33 ms. The calculated worst-case execution time of 0.393 ms is well below this limit. This result indicates that the designed custom instruction is suitable for timing requirements in real-time autonomous systems.
