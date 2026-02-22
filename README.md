<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neonate Yorkie Puppy Tracker v2</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 800px; margin: 0 auto; padding: 20px; background: #f0f8ff; }
        h1 { color: #8b4513; text-align: center; }
        .puppy-section { border: 1px solid #ddd; margin: 20px 0; padding: 15px; border-radius: 8px; background: white; }
        input, select, textarea { width: 100%; padding: 8px; margin: 5px 0; box-sizing: border-box; }
        button { background: #4CAF50; color: white; padding: 10px 20px; border: none; border-radius: 4px; cursor: pointer; margin: 5px 0; }
        button:hover { background: #45a049; }
        .export { background: #2196F3; }
        table { width: 100%; border-collapse: collapse; margin-top: 10px; }
        th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
        th { background-color: #f2f2f2; }
        .alert { color: red; font-weight: bold; }
        .warning { background: #fff3cd; padding: 10px; border-radius: 4px; margin: 10px 0; }
        .growth-chart { background: #e6f3ff; padding: 10px; margin: 10px 0; font-size: 0.9em; }
        canvas { max-width: 100%; height: 200px; }
    </style>
</head>
<body>
    <h1>Neonate Yorkie Puppy Tracker v2</h1>
    <p>Enhanced for your orphaned Yorkie neonates: Logs, diagnostics (fading alerts), trends, export. Log post every-2hr feed.[web:15][cite:9]</p>
    <section id="puppies"></section>

    <script>
        let puppies = JSON.parse(localStorage.getItem('puppies')) || [
            { id: 1,
