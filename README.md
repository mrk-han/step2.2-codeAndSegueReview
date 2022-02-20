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
```

## Code + Segue

<img width="702" alt="image" src="https://user-images.githubusercontent.com/22263679/154866111-e6f563e8-6e99-4d5c-a7f9-556804d65686.png">
<img width="213" alt="image" src="https://user-images.githubusercontent.com/22263679/154866137-ce8253d9-1eff-4d44-96ad-efe226b1d152.png">
Trigger segue with @IBAction func rollDice() on button with code -> `self.performSegue(withIdentifier: "rollDice", sender: self)`

## Segue (No Code)

<img width="1177" alt="image" src="https://user-images.githubusercontent.com/22263679/154866263-11cb0c9b-fafb-493e-9203-4e9bbcbcde9f.png">
