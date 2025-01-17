# embed-htlm-
/** ...simple malware */
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Enemy Software Alert</title>
</head>
<body>
    <h1>Enemy Software Detection</h1>
    <p>
        <?php
            // This is a PHP block embedded in HTML
            $enemySoftware = "Malware";
            echo "Warning: Detected $enemySoftware on your system!";
        ?>
    </p>
</body>
</html>

//malware indicattor 
<?php
// Define known malicious files and processes
$malicious_files = [
    '/path/to/malicious_file1.exe',
    '/path/to/malicious_file2.dll'
];

$malicious_processes = [
    'malicious_process1',
    'malicious_process2'
];

// Function to check for malicious files
function check_files($files) {
    foreach ($files as $file) {
        if (file_exists($file)) {
            echo "Malicious file detected: $file\n";
        }
    }
}

// Function to check for malicious processes
function check_processes($processes) {
    $output = [];
    exec('tasklist', $output);

    foreach ($processes as $process) {
        foreach ($output as $line) {
            if (strpos($line, $process) !== false) {
                echo "Malicious process detected: $process\n";
            }
        }
    }
}
//how to acquire ip adress 
// Check for malicious files and processes
check_files($malicious_files);
check_processes($malicious_processes);

echo "Scan complete.\n";
?>
//to acquire ip adress 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>IP Detection</title>
</head>
<body>
    <h1>Your IP Address</h1>
    <p id="ip-address">
        <?php
            // Function to get the user's IP address
            function getUserIP() {
                // Check if IP is passed from shared internet
                if (!empty($_SERVER['HTTP_CLIENT_IP'])) {
                    $ip = $_SERVER['HTTP_CLIENT_IP'];
                // Check if IP is passed from a proxy
                } elseif (!empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
                    $ip = $_SERVER['HTTP_X_FORWARDED_FOR'];
                // Get the IP address from the remote address
                } else {
                    $ip = $_SERVER['REMOTE_ADDR'];
                }
                return $ip;
            }

            // Get and display the user's IP address
            echo getUserIP();
        ?>
    </p>
</body>
</html>
//


//how to redirect activity 
<?php
// The URL you want to redirect to
$new_url = 'https://www.example.com';

// Use the header function to redirect
header('Location: ' . $new_url);

// Ensure no further code is executed after the redirect
exit();
?>
