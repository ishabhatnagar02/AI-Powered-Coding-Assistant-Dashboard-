# AI-Powered-Coding-Assistant-Dashboard-
I'll create an impressive project that showcases your web development skills. For an internship application, I'll build a modern **AI-Powered Coding Assistant Dashboard** - a practical tool for developers with features like code formatting, syntax highlighting, and real-time previews. This will demonstrate your skills in:

- Clean, responsive UI design
- Interactive JavaScript functionality
- Professional project organization
- Practical developer tools implementation

Here's a complete, single HTML file solution:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CodeSync | AI-Powered Developer Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        :root {
            --primary: #6366f1;
            --secondary: #8b5cf6;
            --dark: #1e293b;
            --light: #f8fafc;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f1f5f9;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        .prose pre {
            background-color: #1e293b;
            border-radius: 0.5rem;
            padding: 1rem;
            overflow-x: auto;
        }
        
        .code-editor {
            height: 500px;
        }
        
        .shadow-lg {
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        .transition-all {
            transition-property: all;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        
        #outputFrame {
            width: 100%;
            height: 100%;
            border: none;
            background-color: white;
            border-radius: 0.5rem;
        }
    </style>
</head>
<body class="min-h-screen">
    <div class="gradient-bg text-white">
        <header class="container mx-auto px-6 py-8">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <i class="fas fa-code text-2xl"></i>
                    <h1 class="text-2xl font-bold">CodeSync</h1>
                </div>
                <nav>
                    <ul class="flex space-x-6">
                        <li><a href="#" class="hover:underline">Features</a></li>
                        <li><a href="#" class="hover:underline">Docs</a></li>
                        <li><a href="#" class="hover:underline">About</a></li>
                    </ul>
                </nav>
                <button class="bg-white text-indigo-600 px-4 py-2 rounded-md font-medium hover:bg-opacity-90 transition-all">
                    Sign In
                </button>
            </div>
            
            <div class="mt-16 text-center">
                <h2 class="text-4xl md:text-5xl font-bold mb-4">AI-Powered Developer Dashboard</h2>
                <p class="text-xl max-w-2xl mx-auto opacity-90">The ultimate tool for writing, formatting, and previewing your code in real-time</p>
                <div class="mt-8 flex justify-center space-x-4">
                    <button class="bg-white text-indigo-600 px-6 py-3 rounded-md font-medium hover:bg-opacity-90 transition-all">
                        Try Demo
                    </button>
                    <button class="border-2 border-white text-white px-6 py-3 rounded-md font-medium hover:bg-white hover:bg-opacity-10 transition-all">
                        GitHub Repo
                    </button>
                </div>
            </div>
        </header>
    </div>

    <main class="container mx-auto px-6 py-12">
        <div class="flex flex-col lg:flex-row gap-8">
            <!-- Editor Column -->
            <div class="w-full lg:w-1/2">
                <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                    <div class="bg-gray-100 px-4 py-3 border-b flex justify-between items-center">
                        <div class="flex space-x-2">
                            <div class="w-3 h-3 rounded-full bg-red-500"></div>
                            <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                            <div class="w-3 h-3 rounded-full bg-green-500"></div>
                        </div>
                        <select id="languageSelect" class="bg-white border border-gray-300 rounded px-3 py-1 text-sm">
                            <option value="html">HTML</option>
                            <option value="css">CSS</option>
                            <option value="javascript">JavaScript</option>
                        </select>
                    </div>
                    <textarea id="codeEditor" class="w-full h-96 p-4 font-mono text-gray-800 focus:outline-none resize-none" spellcheck="false"></textarea>
                    <div class="bg-gray-100 px-4 py-3 border-t flex justify-end space-x-2">
                        <button id="formatBtn" class="bg-indigo-600 text-white px-4 py-2 rounded-md text-sm hover:bg-indigo-700 transition-all">
                            <i class="fas fa-magic mr-2"></i> Format
                        </button>
                        <button id="runBtn" class="bg-green-600 text-white px-4 py-2 rounded-md text-sm hover:bg-green-700 transition-all">
                            <i class="fas fa-play mr-2"></i> Run
                        </button>
                        <button id="clearBtn" class="bg-gray-200 text-gray-700 px-4 py-2 rounded-md text-sm hover:bg-gray-300 transition-all">
                            <i class="fas fa-trash-alt mr-2"></i> Clear
                        </button>
                    </div>
                </div>

                <div class="mt-8 bg-white rounded-xl shadow-lg overflow-hidden">
                    <div class="bg-gray-100 px-4 py-3 border-b">
                        <h3 class="font-medium text-gray-700">AI Code Assistant</h3>
                    </div>
                    <div class="p-4">
                        <div class="flex space-x-2 mb-2">
                            <button class="ai-prompt-btn bg-gray-100 text-gray-700 px-3 py-1 rounded-md text-sm hover:bg-gray-200 transition-all" data-prompt="Explain the following code:">
                                Explain
                            </button>
                            <button class="ai-prompt-btn bg-gray-100 text-gray-700 px-3 py-1 rounded-md text-sm hover:bg-gray-200 transition-all" data-prompt="Optimize this code:">
                                Optimize
                            </button>
                            <button class="ai-prompt-btn bg-gray-100 text-gray-700 px-3 py-1 rounded-md text-sm hover:bg-gray-200 transition-all" data-prompt="Fix bugs in this code:">
                                Debug
                            </button>
                        </div>
                        <textarea id="aiOutput" class="w-full h-32 p-3 border rounded-md resize-none" placeholder="AI output will appear here..." readonly></textarea>
                    </div>
                </div>
            </div>

            <!-- Preview Column -->
            <div class="w-full lg:w-1/2">
                <div class="bg-white rounded-xl shadow-lg overflow-hidden h-full">
                    <div class="bg-gray-100 px-4 py-3 border-b">
                        <h3 class="font-medium text-gray-700">Live Preview</h3>
                    </div>
                    <iframe id="outputFrame" class="w-full h-[500px]"></iframe>
                </div>

                <div class="mt-8 bg-white rounded-xl shadow-lg overflow-hidden">
                    <div class="bg-gray-100 px-4 py-3 border-b">
                        <h3 class="font-medium text-gray-700">Project Stats</h3>
                    </div>
                    <div class="p-4 grid grid-cols-3 gap-4">
                        <div class="text-center">
                            <div class="text-3xl font-bold text-indigo-600" id="charCount">0</div>
                            <div class="text-sm text-gray-500">Characters</div>
                        </div>
                        <div class="text-center">
                            <div class="text-3xl font-bold text-indigo-600" id="lineCount">0</div>
