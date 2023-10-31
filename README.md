<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Feedbacks Formular</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            min-height: 100vh;
            background-color: #BBBCBC;
        }
        .container {
            max-width: 600px;
            padding: 20px;
        }
        .rating-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        .rating-option {
            flex-basis: calc(20% - 10px);
            margin-bottom: 10px;
            cursor: pointer;
            font-size: 16px;
        }
        #missingItemsComments {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Feedback Form</h1>
        <hr>
        <p>Thanks for taking your time, to give us Feedback.</p>
        <form id="feedbackForm" action="#">
            <label for="packaging">How would you rate the quality and condition of the packaging of the goods you received? </label>
            <select id="packaging" name="packaging" required>
                <option value="Excellent">Excellent</option>
                <option value="Good">Good</option>
                <option value="Fair">Fair</option>
                <option value="Poor">Poor</option>
            </select><br><br>
    
            <label for="ontime">Was your order delivered on time, according to your expected delivery date or timeframe? </label>
            <select id="ontime" name="ontime" required>
                <option value="Yes">Yes</option>
                <option value="No">No</option>
            </select><br><br>
    
            <label>How would you rate the quality of the goods you received?</label>
            <div class="rating-container">
                <div>
                    <input type="radio" id="rating1" name="quality" value="1" required>
                    <label for="rating1">Poor</label>
                </div>
                <div>
                    <input type="radio" id="rating2" name="quality" value="2">
                    <label for="rating2">Fair</label>
                </div>
                <div>
                    <input type="radio" id="rating3" name="quality" value="3">
                    <label for="rating3">Good</label>
                </div>
                <div>
                    <input type="radio" id="rating4" name="quality" value="4">
                    <label for="rating4">Very good</label>
                </div>
                <div>
                    <input type="radio" id="rating5" name="quality" value="5">
                    <label for="rating5">Excellent</label>
                </div>
            </div>
            <input type="hidden" id="selectedRating" name="quality" value="" required>
            <br><br>
    
            <label for="missingItems">Did you receive all the items in your order?</label>
            <input type="radio" id="missingItemsYes" name="missingItems" value="Yes">
            <label for="missingItemsYes">Yes</label>
            <input type="radio" id="missingItemsNo" name="missingItems" value="No">
            <label for="missingItemsNo">No</label>
            <br><br>
            <div id="missingItemsComments">
                <label for="missingItemsComment">Please provide details of the missing items:</label><br>
                <textarea id="missingItemsComment" name="missingItemsComment" rows="4" cols="50"></textarea><br><br>
            </div>
    
    
            <label for="supportQuality">How would you rate the quality of our customer support?</label>
            <select id="supportQuality" name="supportQuality" required>
                <option value="Excellent">Excellent</option>
                <option value="Good">Good</option>
                <option value="Fair">Fair</option>
                <option value="Poor">Poor</option>
            </select><br><br>
            <label for="supportComment">Please provide specific information or comments about your experience with customer support:</label><br>
            <textarea id="supportComment" name="supportComment" rows="4" cols="50"></textarea><br><br>
    
    
            <label for="feedback">Any additional comments or suggestions for improvement:</label><br>
            <textarea id="feedback" name="feedback" rows="4" cols="50"></textarea><br><br>
    
            <button type="submit">Submit</button>
        </form>
    
        <script>
            const ratingOptions = document.querySelectorAll('.rating-option');
            const selectedRatingInput = document.getElementById('selectedRating');
            const missingItemsYes = document.getElementById('missingItemsYes');
            const missingItemsComments = document.getElementById('missingItemsComments');
            const missingItemsCommentInput = document.getElementById('missingItemsComment');
    
            ratingOptions.forEach(option => {
                option.addEventListener('click', () => {
                    ratingOptions.forEach(option => option.classList.remove('selected'));
                    option.classList.add('selected');
                    selectedRatingInput.value = option.getAttribute('data-rating');
                });
            });
    
            missingItemsYes.addEventListener('click', () => {
                missingItemsComments.style.display = 'block';
                missingItemsCommentInput.setAttribute('required', 'required');
            });
    
            const missingItemsNo = document.getElementById('missingItemsNo');
            missingItemsNo.addEventListener('click', () => {
                missingItemsComments.style.display = 'none';
                missingItemsCommentInput.removeAttribute('required');
            });
        </script>
    </body>
    </html>
    
