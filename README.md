# step2.2-codeAndSegueReview
Exploring segue from storyboard to code and presenting view controllers
<img width="1051" alt="image" src="https://user-images.githubusercontent.com/22263679/154865910-3c92d181-f602-4690-a7c2-a3fbb2c34071.png">

## Code Only
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
```
