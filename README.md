<?php

$animals = array(
	'Africa' => array('Lycaon pictus', 'Okapia johnstoni', 'Macroscelidea'),
	'Australia' => array('Macropus', 'Dromaius novaehollandiae', 'Vombatidae'),
	'South America' => array('Folivora', 'Cingulata', 'Panthera onca')
);

foreach($animals as $k => $v)
{
	$continent = $k;
	foreach ($v as $animal)
	{
		if (strpos($animal, ' ')) {
			$new_animals[] = $animal;
		}
	}
}

print_r($new_animals);

$names = implode(" ", $new_animals);
echo $names;
$new_names = explode(" ", $names);
$j = count($new_names);
print_r($new_names);

for ($i = 0; $i < $j; $i++) {
	if ($i % 2 == 0) {
		$even[] = $new_names[$i];
	} else {
		$odd[] = $new_names[$i];
	}
}

print_r($even);
print_r($odd);

$even[] = shuffle($even);
array_pop($even);
$odd[] = shuffle($odd);
array_pop($odd);

print_r($even);
print_r($odd);

for ($i = 0; $i < count($even); $i++) {
	$end_names[$i] = $even[$i]." ".$odd[$i];
}

print_r($end_names);

?>
