# Get values
Created Montag 07 Oktober 2019

get() -> Option<&V>
-------------------
let score = scores.get(&team_name);
let score = scores.get("Yellow");
let number = numbers.get(&1);

for with keys()
---------------

### and match
for k in scores.keys() {
println!("Normal: Key '{}': {}", k, match scores.get(k) {Some(value) => value, None => &0});
}

### and unwrap
for k in scores.keys() {
println!("Unwrap: Key '{}': {}", k, scores.get(k).unwrap_or(&0)); 
}

for with tuples()
-----------------
for (key, value) in &scores {
println!("{}: {}", key, value);
}

