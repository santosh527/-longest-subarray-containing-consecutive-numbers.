# -longest-subarray-containing-consecutive-numbers.
Assignment

<?php

function longestSubarray($nums) {
    if (empty($nums)) {
        return [];
    }

    sort($nums); 

    $currentarray = [$nums[0]];
    $longestarray = [$nums[0]];

    for ($i = 1; $i < count($nums); $i++) {
        if ($nums[$i] == $nums[$i - 1] + 1) {
            
            $currentarray[] = $nums[$i];
        } elseif ($nums[$i] != $nums[$i - 1]) {
          
            $currentarray = [$nums[$i]];
        }

       
        if (count($currentarray) > count($longestarray)) {
            $longestarray = $currentarray;
        }
    }

    return $longestarray;
}


$inputArray = [1, 2, 3, 5, 6, 7, 8];
$result = longestSubarray($inputArray);
print_r($result);

?>

