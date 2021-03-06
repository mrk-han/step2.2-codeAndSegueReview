# step2.2-codeAndSegueReview
Exploring segue from storyboard to code and presenting view controllers
<img width="1051" alt="image" src="https://user-images.githubusercontent.com/22263679/154865910-3c92d181-f602-4690-a7c2-a3fbb2c34071.png">

## Code Only (Present ViewControllers Programmatically)

```
@IBAction func rollTheDice() {

    // Get the DiceViewController
    let controller: DiceViewController
    controller = storyboard?.instantiateViewController(withIdentifier: "DiceViewController") as! DiceViewController

    // Set the two values to random numbers from 1 to 6
    controller.firstValue = randomDiceValue()
    controller.secondValue = randomDiceValue()

    // Present the view Controller
    present(controller, animated: true, completion: nil)
}

^ Above sets up new ViewController, passes data AND presents new ViewController
```

## Code + Segue

<img width="702" alt="image" src="https://user-images.githubusercontent.com/22263679/154866111-e6f563e8-6e99-4d5c-a7f9-556804d65686.png">
<img width="213" alt="image" src="https://user-images.githubusercontent.com/22263679/154866137-ce8253d9-1eff-4d44-96ad-efe226b1d152.png">
Trigger segue with @IBAction func rollDice() on button with code -> `self.performSegue(withIdentifier: "rollDice", sender: self)`

Above only sets up the Segue and New ViewController but does not connect two ViewControllers

## Segue (No Code)

<img width="1177" alt="image" src="https://user-images.githubusercontent.com/22263679/154866263-11cb0c9b-fafb-493e-9203-4e9bbcbcde9f.png">


Notice that:

In the RollViewController file, the rollTheDice method is empty.

In the Storyboard file, a segue connects the rollTheDice Button directly to the DiceViewController.

In the attributes inspector, the segue is given the identifier, “rollDice”.

Again, this only sets up the Segue and hides the instantiation of the new ViewController behind the story board, but does not pass data.

## Passing data when using the 2nd and 3rd example (Code + Segue, and Segue)

<img width="1011" alt="image" src="https://user-images.githubusercontent.com/22263679/154866486-fead8b49-d1f6-489d-bc78-9c7510b17053.png">

We need to override the func prepare(for segue: UIStoryboardSegue, sender: Any?) method

We then cast `DiceViewController` as the `segue.destination` and then can pass the data to the ViewController that presents the dice.

## If more than one segue attached to a ViewController

<img width="1030" alt="image" src="https://user-images.githubusercontent.com/22263679/154866971-8b50fed9-c03a-4361-9ab3-3369415c0a46.png">

Use `if segue.identifier == "nameOfSegue" {` when we have more than one segue attached to a single ViewController
