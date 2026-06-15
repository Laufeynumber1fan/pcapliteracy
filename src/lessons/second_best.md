<h1 id="h-note"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/raw/refs/heads/gh-pages/material/second%20best.pcap">Second Best</h1></a>
> [!NOTE]  
> How do you read a pcap with a space in the name?

<div class="container">
    <div class="form-row">
        <div class="container">
            <hr>
            <ol>
                <li>
                    <p>What is the MD5 hash of the pcap?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="761a88362119f2ca571eb2b82e04ef90" data-question="7s6s1sas8s8s3s6s2s1s1s9sfs2scsas5s7s1sesbs2sbs8s2ses0s4sesfs9s0s" placeholder="********************************" maxlength="32" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the Arrival timestamp of the 722nd packet?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="15:45:32 13-30-5202" data-question="1s5s:s4s5s:s3s2s s1s3s-s3s0s-s5s2s0s2s" placeholder="YYYY-MM-DD HH-MM-SS" maxlength="19" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Identify domains that were contacted in the pcap. <em>Select all that apply.</em></p>
                    <ul class="checklist">
                        <li><label><input type="checkbox" data-question="moc.elgoog" data-content="1" /> google.com</label></li>
                        <li><label><input type="checkbox" data-question="moc.ebutuoy" data-content="0" /> youtube.com</label></li>
                        <li><label><input type="checkbox" data-question="moc.gnib" data-content="0" /> bing.com</label></li>
                        <li><label><input type="checkbox" data-question="moc.oohay" data-content="0" /> yahoo.com</label></li>
                        <li><label><input type="checkbox" data-question="moc.tfosorcim" data-content="1" /> microsoft.com</label></li>
                        <li><label><input type="checkbox" data-question="ur.sursrekcah" data-content="0" /> hackersrus.ru</label></li>
                        <li><label><input type="checkbox" data-question="moc.latotsuriv" data-content="0" /> virustotal.com</label></li>
                    </ul>
                </li>
                <li>
                    <p>How many tcp streams are in the pcap?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="71" data-question="7s1s" placeholder="**" maxlength="2" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Are there malicious exe files in this pcap?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=".selif" data-content="0" /> No. There are no exe files.</label></li>
                        <li><label><input type="radio" data-question=".esu" data-content="0" /> No. All files are safe to use.</label></li>
                        <li><label><input type="radio" data-question=".selif" data-content="0" /> Yes. There are malicious .crl files.</label></li>
                        <li><label><input type="radio" data-question=".LSS" data-content="1" /> Unsure. The files are encrypted with SSL.</label></li>
                    </ul>
                </li>
            </ol>
        </div>
    </div>
    <div id="tg-msg" class="alert" role="alert" style="display: none">
        <span id="tg-correct-questions"></span> Correct! <br /><b>Rating: <span id="tg-score"></span>%</b>
    </div>
    <div class="row">
        <button id="check-questions" class="btn btn-lg btn-success">Check</button>
        <button id="reset-questions" class="btn btn-link">Reset All</button>
</div>
<script type="text/javascript">//console.log("Check");
    $(function(){
        $('ul.radio-list,ul.checklist,ul.textbox').each(function(i, el){
            var questionClass = $(this).attr('class');
            $(this).parent().addClass('question-row').addClass(questionClass);
            if (questionClass=='radio-list') {
                $(this).find('input[type="radio"]').attr('name', 'radio-question-' + i);
            }
        });
        function checkQuestion() {
            resetQuestions(true);
            var questions = $('li.question-row');
            var total_questions = questions.length;
            var correct = 0;
            questions.each(function(i, el) {
                var self = $(this);
                // Single Question.
                if (self.hasClass('radio-list')) {
                    //if correct, save data-question as localStorage key
                    //Will use key-value to reenter answers at startup
                    if (self.find('input[type="radio"][data-content="1"]:checked').length == 1) {
                        var checkbox = self.find('input[type="radio"]');
                        var question = String(checkbox.data("question"));
                        localStorage.setItem(question, true);
                        correct += 1;
                    } else {
                        self.addClass('text-danger');
                    }
                }
                // Textbox Question.
                if(self.hasClass('textbox')) {
                    var textbox = self.find('input[type="text"]');
                    var current_text = String(textbox.val()).trim().toLowerCase();
                    var correct_text = String(textbox.data("content")).trim().split("").reverse().join("");
                    var question = String(textbox.data("question"));
                    if(current_text==correct_text.toLowerCase()) {
                        correct += 1;
                        localStorage.setItem(question, textbox.data("content"));
                    } else {
                        self.addClass('text-danger');
                        textbox.parent().find("i.text-correct").html(correct_text);
                    }
                }
                // Multiple selection Questions.
                if(self.hasClass('checklist')) {
                    var total_corrects = self.find('input[type="checkbox"][data-content="1"]').length;
                    var total_incorrects = self.find('input[type="checkbox"][data-content="0"]').length;
                    var correct_selected = self.find('input[type="checkbox"][data-content="1"]:checked').length;
                    var incorrect_selected = self.find('input[type="checkbox"][data-content="0"]:checked').length;
                    var qc = +((correct_selected / total_corrects) - (incorrect_selected/total_incorrects)).toFixed(2);
                    if (qc < 0) {
                        qc = 0;
                    } else if (qc == 1) {
                        var checkbox = self.find('input[type="checkbox"]');
                        var question = String(checkbox.data("question"));
                        localStorage.setItem(question, true);
                    }
                    correct += qc;
                    if (qc == 0) {
                        self.addClass('text-danger');
                    } else if (qc > 0 && qc < 1) {
                        self.addClass('text-warning');
                    }
                }
            });
            showScore(correct, total_questions);
        }
        function showScore(correct, total) {
            var score = (correct / total).toFixed(2) * 100;
            var msgClass = 'alert-danger';
            if (score >= 70) {
                msgClass = 'alert-success';
            } else if (score >= 50) {
                msgClass = 'alert-warning';
            }
            $('#tg-correct-questions').text(correct + ' out of ' + total);
            $('#tg-score').text(score);
            $('#tg-msg').addClass(msgClass).show();
        }
        function resetQuestions(keep) {
            $('li.question-row').removeClass('text-danger').removeClass('text-warning');
            $('i.text-correct').html('');
            $('#tg-msg').removeClass('alert-danger').removeClass('alert-success').removeClass('alert-warning').hide();
            if(keep === true) {
                return;
            }
            $('li.question-row').find('input[type="text"]').val('');
            $('li.question-row').find('input[type="radio"],input[type="checkbox"]').prop('checked', false);
        }
        $('#check-questions').on('click', checkQuestion);
        $('#reset-questions').on('click', resetQuestions);
    });
    //On document ready, reenter saved answers and click the "Check" button
    $(document).ready(function () {
        var previously_answered = false;
        //for loop for localStorage values
        $.each(Object.keys(localStorage), function(i, key) {
            const value = localStorage.getItem(key);
            var questions = $('li.question-row');
            questions.each(function(i, el) {
                var self = $(this);
                if (self.find('[data-question]').data("question") == key) {
                        //answers are recreated
                        if (self.hasClass('radio-list')) {
                        self.find('input[type="radio"][data-content="1"]')[0].checked = true;
                        } else if (self.hasClass('textbox')) {
                        self.find('input[type="text"]')[0].value = value.trim().split("").reverse().join("");
                        } else if (self.hasClass('checklist')) {
                        var checkboxes = self.find('input[type="checkbox"][data-content="1"]');
                        for(var y = 0; y < checkboxes.length; y++){
                            checkboxes[y].checked = true;
                        }
                    }
                    //value saved for any key match, value is used to check if the button needs to be pressed
                    previously_answered = true;
                };
            });
        });
        if (previously_answered) {
                document.getElementById("check-questions").click();
        }
    });
</script>
