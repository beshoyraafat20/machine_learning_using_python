<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Regression Cheat Sheet - Code Only</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom styles for code blocks within the table */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #1a202c; /* Dark background */
            color: #e2e8f0; /* Light text */
        }
        .code-container {
            background-color: #2d3748; /* Slightly lighter dark for code blocks */
            border-radius: 0.5rem; /* Rounded corners for code blocks */
            padding: 0.75rem;
            overflow-x: auto; /* Enable horizontal scrolling for long lines */
            font-family: 'Fira Code', 'Cascadia Code', 'Consolas', monospace; /* Monospaced font for code */
            font-size: 0.875rem; /* Smaller font size for code */
            line-height: 1.5;
            color: #a0aec0; /* Lighter grey for code text */
        }
        .code-container pre {
            margin: 0; /* Remove default margin from pre */
        }
        .code-container code {
            display: block; /* Ensure code block takes full width */
            white-space: pre; /* Preserve whitespace and line breaks */
        }
        .code-line {
            display: flex;
            align-items: flex-start;
        }
        .line-number {
            color: #4a5568; /* Darker grey for line numbers */
            margin-right: 0.75rem;
            text-align: right;
            min-width: 1.5rem; /* Ensure line numbers have consistent width */
            user-select: none; /* Prevent selection of line numbers */
        }
        /* Basic syntax highlighting (manual for demonstration) */
        .keyword { color: #81e6d9; } /* Teal */
        .function { color: #63b3ed; } /* Blue */
        .string { color: #f6ad55; } /* Orange */
        .variable { color: #a0aec0; } /* Light grey */
        .comment { color: #718096; } /* Grey */
        .number { color: #fc8181; } /* Red */
    </style>
</head>
<body class="p-4 sm:p-8">

    <div class="max-w-4xl mx-auto bg-gray-800 p-6 sm:p-8 rounded-lg shadow-xl">
        <h1 class="text-3xl sm:text-4xl font-bold text-center mb-8 text-white">
            Regression Cheat Sheet - Code Only
        </h1>

        <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse">
                <thead>
                    <tr class="bg-gray-700">
                        <th class="py-3 px-4 border-b border-gray-600 text-gray-200 text-lg rounded-tl-lg">Model Name</th>
                        <th class="py-3 px-4 border-b border-gray-600 text-gray-200 text-lg rounded-tr-lg">Code Syntax</th>
                    </tr>
                </thead>
                <tbody>
                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100">Simple Linear Regression</p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.linear_model</span> <span class="keyword">import</span> <span class="variable">LinearRegression</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">model</span> = <span class="function">LinearRegression</span>()</span>
<span class="code-line"><span class="line-number">3</span><span class="variable">model</span>.fit(X, y)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100">Polynomial Regression</p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.preprocessing</span> <span class="keyword">import</span> <span class="variable">PolynomialFeatures</span></span>
<span class="code-line"><span class="line-number">2</span><span class="keyword">from</span> <span class="function">sklearn.linear_model</span> <span class="keyword">import</span> <span class="variable">LinearRegression</span></span>
<span class="code-line"><span class="line-number">3</span><span class="variable">poly</span> = <span class="function">PolynomialFeatures</span>(<span class="variable">degree</span>=2)</span>
<span class="code-line"><span class="line-number">4</span>X_poly = <span class="variable">poly</span>.fit_transform(X)</span>
<span class="code-line"><span class="line-number">5</span><span class="variable">model</span> = <span class="function">LinearRegression</span>().fit(X_poly, y)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100">Multiple Linear Regression</p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.linear_model</span> <span class="keyword">import</span> <span class="variable">LinearRegression</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">model</span> = <span class="function">LinearRegression</span>()</span>
<span class="code-line"><span class="line-number">3</span><span class="variable">model</span>.fit(X, y)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100">Logistic Regression</p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.linear_model</span> <span class="keyword">import</span> <span class="variable">LogisticRegression</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">model</span> = <span class="function">LogisticRegression</span>()</span>
<span class="code-line"><span class="line-number">3</span><span class="variable">model</span>.fit(X, y)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>train_test_split</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.model_selection</span> <span class="keyword">import</span> <span class="variable">train_test_split</span></span>
<span class="code-line"><span class="line-number">2</span>X_train, X_test, y_train, y_test = <span class="function">train_test_split</span>(X, y, <span class="variable">test_size</span>=0.2, <span class="variable">random_state</span>=42)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>StandardScaler</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.preprocessing</span> <span class="keyword">import</span> <span class="variable">StandardScaler</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">scaler</span> = <span class="function">StandardScaler</span>()</span>
<span class="code-line"><span class="line-number">3</span>X_scaled = <span class="variable">scaler</span>.fit_transform(X)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>log_loss</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.metrics</span> <span class="keyword">import</span> <span class="variable">log_loss</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">loss</span> = <span class="function">log_loss</span>(y_true, y_pred_proba)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>mean_absolute_error</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.metrics</span> <span class="keyword">import</span> <span class="variable">mean_absolute_error</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">mae</span> = <span class="function">mean_absolute_error</span>(y_true, y_pred)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>mean_squared_error</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.metrics</span> <span class="keyword">import</span> <span class="variable">mean_squared_error</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">mse</span> = <span class="function">mean_squared_error</span>(y_true, y_pred)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 border-b border-gray-700 align-top">
                            <p class="font-semibold text-gray-100"><code>root_mean_squared_error</code></p>
                        </td>
                        <td class="py-4 px-4 border-b border-gray-700">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.metrics</span> <span class="keyword">import</span> <span class="variable">mean_squared_error</span></span>
<span class="code-line"><span class="line-number">2</span><span class="keyword">import</span> <span class="variable">numpy</span> <span class="keyword">as</span> <span class="variable">np</span></span>
<span class="code-line"><span class="line-number">3</span><span class="variable">rmse</span> = <span class="variable">np</span>.<span class="function">sqrt</span>(<span class="function">mean_squared_error</span>(y_true, y_pred))</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>

                    <tr class="hover:bg-gray-700 transition-colors duration-200">
                        <td class="py-4 px-4 align-top">
                            <p class="font-semibold text-gray-100"><code>r2_score</code></p>
                        </td>
                        <td class="py-4 px-4">
                            <div class="code-container">
                                <pre><code>
<span class="code-line"><span class="line-number">1</span><span class="keyword">from</span> <span class="function">sklearn.metrics</span> <span class="keyword">import</span> <span class="variable">r2_score</span></span>
<span class="code-line"><span class="line-number">2</span><span class="variable">r2</span> = <span class="function">r2_score</span>(y_true, y_pred)</span>
                                </code></pre>
                            </div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>

</body>
</html>
