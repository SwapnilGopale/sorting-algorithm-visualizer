<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sorting Algorithm Comparison Visualizer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #3b82f6; /* Blue-500 */
            --compare-color: #ef4444; /* Red-500 */
            --swap-color: #f59e0b; /* Amber-500 */
            --sorted-color: #10b981; /* Emerald-500 */
        }
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6;
            min-height: 100vh;
        }
        .canvas-container {
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
            transition: transform 0.2s;
            overflow: hidden;
        }
        .canvas-container:hover {
            transform: translateY(-2px);
        }
    </style>
</head>
<body class="p-4 sm:p-8">

    <header class="text-center mb-8">
        <h1 class="text-3xl sm:text-4xl font-extrabold text-gray-800">Sorting Algorithm Visualizer</h1>
        <p class="text-gray-500 mt-1">Comparing 10 algorithms side-by-side on identical data.</p>
    </header>

    <!-- Controls Panel -->
    <div class="bg-white p-4 sm:p-6 rounded-xl shadow-lg mb-8 max-w-4xl mx-auto">
        <div class="flex flex-col sm:flex-row justify-between items-center space-y-4 sm:space-y-0 sm:space-x-4">
            <!-- Array Size Control -->
            <div class="w-full sm:w-1/3">
                <label for="arraySize" class="block text-sm font-medium text-gray-700 mb-1">Array Size: <span id="sizeValue">50</span></label>
                <input type="range" id="arraySize" min="5" max="100" value="50" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer">
            </div>

            <!-- Speed Control -->
            <div class="w-full sm:w-1/3">
                <label for="speedControl" class="block text-sm font-medium text-gray-700 mb-1">Speed: <span id="speedValue">25</span> ms delay</label>
                <input type="range" id="speedControl" min="1" max="100" value="25" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer">
            </div>

            <!-- Start Button -->
            <button id="startButton" class="w-full sm:w-1/3 bg-blue-600 hover:bg-blue-700 text-white font-semibold py-2 px-4 rounded-lg transition duration-200 shadow-md hover:shadow-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50" onclick="startVisualization()">
                Start Comparison
            </button>
        </div>
    </div>

    <!-- Visualization Grid -->
    <div id="visualizationGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-6 max-w-7xl mx-auto">
        <!-- Canvases will be generated here by JavaScript -->
    </div>

    <script>
        const algorithms = [
            { id: 'bubble', name: 'Bubble Sort', fn: bubbleSort },
            { id: 'selection', name: 'Selection Sort', fn: selectionSort },
            { id: 'insertion', name: 'Insertion Sort', fn: insertionSort },
            { id: 'merge', name: 'Merge Sort', fn: mergeSort },
            { id: 'quick', name: 'Quick Sort', fn: quickSort },
            { id: 'heap', name: 'Heap Sort', fn: heapSort },
            { id: 'counting', name: 'Counting Sort', fn: countingSort },
            { id: 'radix', name: 'Radix Sort', fn: radixSort },
            { id: 'bucket', name: 'Bucket Sort', fn: bucketSort },
            { id: 'shell', name: 'Shell Sort', fn: shellSort },
        ];

        const CANVAS_WIDTH = 300;
        const CANVAS_HEIGHT = 200;
        let originalArray = [];
        let isSorting = false;
        let animationDelay = 25; // Default speed
        let arraySize = 50;

        // UI Element References
        const startButton = document.getElementById('startButton');
        const arraySizeInput = document.getElementById('arraySize');
        const sizeValueSpan = document.getElementById('sizeValue');
        const speedControlInput = document.getElementById('speedControl');
        const speedValueSpan = document.getElementById('speedValue');
        const grid = document.getElementById('visualizationGrid');

        // --- Utility Functions ---

        /** Global sleep function for pacing the visualization. */
        const sleep = (ms) => new Promise(resolve => setTimeout(resolve, ms));

        /** Generates a random array of unique integers. */
        function generateArray(size) {
            const arr = Array.from({ length: size }, (_, i) => i + 1);
            for (let i = arr.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [arr[i], arr[j]] = [arr[j], arr[i]];
            }
            return arr;
        }

        /** Creates the canvas elements in the DOM. */
        function setupCanvases() {
            grid.innerHTML = ''; // Clear previous canvases
            algorithms.forEach(algo => {
                const container = document.createElement('div');
                container.className = 'canvas-container bg-white rounded-lg p-2 flex flex-col transition shadow-md';

                const title = document.createElement('h2');
                title.className = 'text-lg font-semibold text-gray-800 text-center mb-1';
                title.textContent = algo.name;
                container.appendChild(title);

                const status = document.createElement('div');
                status.id = `${algo.id}Status`;
                status.className = 'text-xs text-center h-4 mb-1 font-mono text-gray-500';
                status.textContent = 'Ready';
                container.appendChild(status);

                const canvas = document.createElement('canvas');
                canvas.id = algo.id;
                canvas.width = CANVAS_WIDTH;
                canvas.height = CANVAS_HEIGHT;
                canvas.className = 'border border-gray-200 rounded';
                container.appendChild(canvas);

                grid.appendChild(container);
            });
        }

        /** Draws the array state on a specific canvas. */
        function drawArray(canvasId, array, colorIndices = {}) {
            const canvas = document.getElementById(canvasId);
            if (!canvas) return;
            const ctx = canvas.getContext('2d');
            ctx.clearRect(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);

            const barWidth = CANVAS_WIDTH / array.length;
            const maxVal = arraySize; // Since we generate values from 1 to arraySize

            for (let i = 0; i < array.length; i++) {
                const value = array[i];
                const barHeight = (value / maxVal) * CANVAS_HEIGHT;

                let color = 'var(--primary-color)'; // Default

                if (colorIndices.compare && (colorIndices.compare.includes(i))) {
                    color = 'var(--compare-color)'; // Red (Comparing)
                } else if (colorIndices.swap && (colorIndices.swap.includes(i))) {
                    color = 'var(--swap-color)'; // Amber (Swapping/Pivot)
                } else if (colorIndices.sorted && (colorIndices.sorted.includes(i))) {
                    color = 'var(--sorted-color)'; // Green (Sorted/Final Position)
                }

                ctx.fillStyle = color;
                ctx.fillRect(i * barWidth, CANVAS_HEIGHT - barHeight, barWidth, barHeight);
            }
        }

        // --- Algorithm Implementations (Async/Generator Functions) ---

        /** Updates the status text for a visualization. */
        function setStatus(id, text, color = 'text-gray-500') {
            const statusElement = document.getElementById(`${id}Status`);
            if (statusElement) {
                statusElement.textContent = text;
                statusElement.className = `text-xs text-center h-4 mb-1 font-mono ${color}`;
            }
        }

        /** Resets the visualization. */
        function resetVisualizer() {
            isSorting = false;
            startButton.textContent = 'Start Comparison';
            startButton.disabled = false;
            algorithms.forEach(algo => {
                const newArray = [...originalArray];
                drawArray(algo.id, newArray);
                setStatus(algo.id, 'Ready', 'text-gray-500');
            });
        }

        // --- Sorting Algorithms ---

        async function bubbleSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            for (let i = 0; i < n - 1; i++) {
                for (let j = 0; j < n - 1 - i; j++) {
                    drawArray(id, array, { compare: [j, j + 1], sorted: Array.from({ length: i }, (_, k) => n - 1 - k) });
                    await sleep(animationDelay);
                    if (array[j] > array[j + 1]) {
                        [array[j], array[j + 1]] = [array[j + 1], array[j]];
                        drawArray(id, array, { swap: [j, j + 1], sorted: Array.from({ length: i }, (_, k) => n - 1 - k) });
                        await sleep(animationDelay);
                    }
                }
            }
            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function selectionSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            for (let i = 0; i < n - 1; i++) {
                let min_idx = i;
                for (let j = i + 1; j < n; j++) {
                    drawArray(id, array, { compare: [j], swap: [min_idx, i], sorted: Array.from({ length: i }, (_, k) => k) });
                    await sleep(animationDelay);
                    if (array[j] < array[min_idx]) {
                        min_idx = j;
                    }
                }
                [array[i], array[min_idx]] = [array[min_idx], array[i]];
            }
            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function insertionSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            for (let i = 1; i < n; i++) {
                let key = array[i];
                let j = i - 1;
                while (j >= 0 && array[j] > key) {
                    array[j + 1] = array[j];
                    drawArray(id, array, { compare: [j, j + 1], swap: [i], sorted: Array.from({ length: i }, (_, k) => k) });
                    await sleep(animationDelay);
                    j = j - 1;
                }
                array[j + 1] = key;
                drawArray(id, array, { swap: [j + 1], sorted: Array.from({ length: i }, (_, k) => k) });
                await sleep(animationDelay);
            }
            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function mergeSort(array, id) {
            setStatus(id, 'Running');

            async function merge(arr, l, m, r) {
                let n1 = m - l + 1;
                let n2 = r - m;
                let L = new Array(n1);
                let R = new Array(n2);

                for (let i = 0; i < n1; i++) L[i] = arr[l + i];
                for (let j = 0; j < n2; j++) R[j] = arr[m + 1 + j];

                let i = 0; let j = 0; let k = l;

                while (i < n1 && j < n2) {
                    drawArray(id, arr, { compare: [l + i, m + 1 + j] });
                    await sleep(animationDelay);
                    if (L[i] <= R[j]) {
                        arr[k] = L[i];
                        i++;
                    } else {
                        arr[k] = R[j];
                        j++;
                    }
                    drawArray(id, arr, { swap: [k], compare: [l + i, m + 1 + j] });
                    await sleep(animationDelay);
                    k++;
                }

                while (i < n1) {
                    arr[k] = L[i];
                    drawArray(id, arr, { swap: [k] });
                    await sleep(animationDelay);
                    i++; k++;
                }

                while (j < n2) {
                    arr[k] = R[j];
                    drawArray(id, arr, { swap: [k] });
                    await sleep(animationDelay);
                    j++; k++;
                }
            }

            async function sort(arr, l, r) {
                if (l >= r) return;
                let m = l + Math.floor((r - l) / 2);
                await sort(arr, l, m);
                await sort(arr, m + 1, r);
                await merge(arr, l, m, r);
            }

            await sort(array, 0, array.length - 1);
            drawArray(id, array, { sorted: Array.from({ length: array.length }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function quickSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;

            async function partition(arr, low, high) {
                let pivot = arr[high];
                let i = (low - 1);

                for (let j = low; j <= high - 1; j++) {
                    drawArray(id, arr, { compare: [j, high], swap: i >= low ? [i, j] : [j], sorted: Array.from({ length: n - (high - low) - 1 }, (_, k) => k) });
                    await sleep(animationDelay);
                    if (arr[j] < pivot) {
                        i++;
                        [arr[i], arr[j]] = [arr[j], arr[i]];
                        drawArray(id, arr, { swap: [i, j], compare: [high] });
                        await sleep(animationDelay);
                    }
                }
                [arr[i + 1], arr[high]] = [arr[high], arr[i + 1]];
                drawArray(id, arr, { swap: [i + 1, high], sorted: [i + 1] });
                await sleep(animationDelay);
                return (i + 1);
            }

            async function sort(arr, low, high) {
                if (low < high) {
                    let pi = await partition(arr, low, high);
                    await sort(arr, low, pi - 1);
                    await sort(arr, pi + 1, high);
                }
            }

            await sort(array, 0, array.length - 1);
            drawArray(id, array, { sorted: Array.from({ length: array.length }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function heapSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;

            async function heapify(arr, n, i) {
                let largest = i;
                let l = 2 * i + 1;
                let r = 2 * i + 2;

                if (l < n && arr[l] > arr[largest]) largest = l;
                if (r < n && arr[r] > arr[largest]) largest = r;

                if (largest !== i) {
                    [arr[i], arr[largest]] = [arr[largest], arr[i]];
                    drawArray(id, arr, { swap: [i, largest] });
                    await sleep(animationDelay);
                    await heapify(arr, n, largest);
                }
                drawArray(id, arr, { compare: [i] });
                await sleep(animationDelay);
            }

            // Build heap (rearrange array)
            for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
                await heapify(array, n, i);
            }

            // One by one extract an element from heap
            for (let i = n - 1; i > 0; i--) {
                [array[0], array[i]] = [array[i], array[0]];
                drawArray(id, array, { swap: [0, i], sorted: Array.from({ length: n - i }, (_, k) => i + k) });
                await sleep(animationDelay);
                await heapify(array, i, 0);
            }

            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function countingSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            let max = array.reduce((a, b) => Math.max(a, b), 0);
            let count = new Array(max + 1).fill(0);
            let output = new Array(n).fill(0);

            // 1. Store count of each element
            for (let i = 0; i < n; i++) {
                count[array[i]]++;
                drawArray(id, array, { compare: [i], swap: [array[i]] });
                await sleep(animationDelay * 0.5); // Faster phase
            }
            setStatus(id, 'Counting', 'text-yellow-600');

            // 2. Change count[i] so that count[i] now contains actual position of this element
            for (let i = 1; i <= max; i++) {
                count[i] += count[i - 1];
            }
            setStatus(id, 'Prefix Sum', 'text-yellow-600');

            // 3. Build the output array
            for (let i = n - 1; i >= 0; i--) {
                output[count[array[i]] - 1] = array[i];
                count[array[i]]--;
                // Visualize placing into output (represented by the original array)
                array[i] = -1; // Temp mark for elements not yet placed
                drawArray(id, [...array, ...output.slice(0, n - i), ...Array(i).fill(0)], { swap: [i] }); // Simplified visualization
                await sleep(animationDelay);
            }

            // 4. Copy the output array to arr
            for (let i = 0; i < n; i++) {
                array[i] = output[i];
                drawArray(id, array, { sorted: Array.from({ length: i + 1 }, (_, k) => k) });
                await sleep(animationDelay);
            }

            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function radixSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            let max = array.reduce((a, b) => Math.max(a, b), 0);

            async function countingSortByDigit(arr, exp) {
                let output = new Array(n).fill(0);
                let count = new Array(10).fill(0);

                // Store count of occurrences in count[]
                for (let i = 0; i < n; i++) {
                    count[Math.floor(arr[i] / exp) % 10]++;
                    drawArray(id, arr, { compare: [i] });
                    await sleep(animationDelay * 0.2);
                }

                // Change count[i] so that count[i] now contains actual position
                for (let i = 1; i < 10; i++) count[i] += count[i - 1];

                // Build the output array
                for (let i = n - 1; i >= 0; i--) {
                    let digit = Math.floor(arr[i] / exp) % 10;
                    output[count[digit] - 1] = arr[i];
                    count[digit]--;
                    drawArray(id, arr, { swap: [i] });
                    await sleep(animationDelay * 0.5);
                }

                // Copy the output array to arr
                for (let i = 0; i < n; i++) {
                    arr[i] = output[i];
                    drawArray(id, arr, { swap: [i] });
                    await sleep(animationDelay * 0.8);
                }
            }

            for (let exp = 1; Math.floor(max / exp) > 0; exp *= 10) {
                setStatus(id, `Pass (Exp: ${exp})`, 'text-yellow-600');
                await countingSortByDigit(array, exp);
            }

            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function bucketSort(array, id) {
            setStatus(id, 'Running');
            const n = array.length;
            const bucketSize = 10;
            const maxVal = arraySize; // Max value is arraySize since we use 1..N
            const bucketCount = Math.floor(maxVal / bucketSize) + 1;
            let buckets = Array.from({ length: bucketCount }, () => []);

            // 1. Distribute elements into buckets
            for (let i = 0; i < n; i++) {
                const bucketIndex = Math.floor(array[i] / bucketSize);
                buckets[bucketIndex].push(array[i]);
                drawArray(id, array, { compare: [i] });
                await sleep(animationDelay * 0.5);
            }
            setStatus(id, 'Bucketing', 'text-yellow-600');

            // 2. Sort each bucket (using Insertion Sort internally for simplicity)
            for (let b = 0; b < bucketCount; b++) {
                let bucket = buckets[b];
                for (let i = 1; i < bucket.length; i++) {
                    let key = bucket[i];
                    let j = i - 1;
                    while (j >= 0 && bucket[j] > key) {
                        bucket[j + 1] = bucket[j];
                        j--;
                    }
                    bucket[j + 1] = key;
                }
                setStatus(id, `Sorting Bucket ${b + 1}`, 'text-orange-600');
                // Visualization update after internal sort (approximation)
                let tempArr = [].concat(...buckets.slice(0, b), bucket, ...buckets.slice(b + 1));
                let offset = [].concat(...buckets.slice(0, b)).length;
                let sortedIndices = Array.from({ length: offset + bucket.length }, (_, k) => k);

                drawArray(id, tempArr, { sorted: sortedIndices, compare: Array.from({ length: bucket.length }, (_, k) => offset + k) });
                await sleep(animationDelay * 2);
            }

            // 3. Concatenate buckets
            let k = 0;
            for (let b = 0; b < bucketCount; b++) {
                for (let val of buckets[b]) {
                    array[k] = val;
                    drawArray(id, array, { sorted: Array.from({ length: k + 1 }, (_, i) => i) });
                    await sleep(animationDelay);
                    k++;
                }
            }

            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }

        async function shellSort(array, id) {
            setStatus(id, 'Running');
            let n = array.length;
            let h = 1;
            while (h < n / 3) h = 3 * h + 1;

            while (h >= 1) {
                for (let i = h; i < n; i++) {
                    for (let j = i; j >= h; j -= h) {
                        drawArray(id, array, { compare: [j, j - h], swap: [i] });
                        await sleep(animationDelay);

                        if (array[j] < array[j - h]) {
                            [array[j], array[j - h]] = [array[j - h], array[j]];
                            drawArray(id, array, { swap: [j, j - h] });
                            await sleep(animationDelay);
                        } else {
                            break;
                        }
                    }
                }
                h = Math.floor(h / 3);
                setStatus(id, `Gap: ${h}`, 'text-yellow-600');
            }
            drawArray(id, array, { sorted: Array.from({ length: n }, (_, k) => k) });
            setStatus(id, 'Complete', 'text-green-600');
        }


        // --- Main Control Logic ---

        async function startVisualization() {
            if (isSorting) return;
            isSorting = true;
            startButton.textContent = 'Sorting...';
            startButton.disabled = true;

            // 1. Generate the shared initial array
            originalArray = generateArray(arraySize);

            // 2. Start all algorithms concurrently
            const sortPromises = algorithms.map(algo => {
                const arrayCopy = [...originalArray];
                // Reset canvas visualization
                drawArray(algo.id, arrayCopy);
                setStatus(algo.id, 'Starting...');
                // Run the algorithm function
                return algo.fn(arrayCopy, algo.id);
            });

            try {
                // Wait for all promises to resolve
                await Promise.all(sortPromises);
            } catch (error) {
                console.error("An algorithm failed:", error);
                setStatus(algorithms.find(a => a.fn === error.algo).id, 'Error', 'text-red-600');
            }

            isSorting = false;
            startButton.textContent = 'Restart Comparison';
            startButton.disabled = false;
        }

        // --- Event Listeners and Initialization ---

        arraySizeInput.addEventListener('input', (e) => {
            if (isSorting) return;
            arraySize = parseInt(e.target.value);
            sizeValueSpan.textContent = arraySize;
            // Re-setup the initial array and canvases
            originalArray = generateArray(arraySize);
            resetVisualizer();
        });

        speedControlInput.addEventListener('input', (e) => {
            animationDelay = parseInt(e.target.value);
            speedValueSpan.textContent = animationDelay;
        });

        // Initial setup on load
        window.onload = () => {
            setupCanvases();
            arraySize = parseInt(arraySizeInput.value);
            originalArray = generateArray(arraySize);
            resetVisualizer();
        };

    </script>
</body>
</html>
