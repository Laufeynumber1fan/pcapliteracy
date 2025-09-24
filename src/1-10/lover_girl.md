<h1 id="h-note"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/blob/gh-pages/pcaps/1-10/lover_girl.pcap">Lover Girl <u>🠇</u></h1>
> [!NOTE]  
> Please **google** if you don't know what to do.

<div class="container">
    <div class="form-row">
        <div class="container">
                <hr>
                <ol>
                    <li>
                        <p>What version of Apache is the web server using?</p>
                        <ul class="textbox">
                            <li><input type="text" data-content="04.0.2" data-question="0s4s.s0s.s2s" placeholder="*.*.**" maxlength="6" class="form-control" />
                        </ul>
                    </li>
                    <li>
                        <p>What is the "Last Modified" timestamp of bg2.jpg?</p>
                        <ul class="textbox">
                            <li><input type="text" data-content="00:00:50 21-10-1002" data-question="0s0s:s0s0s:s5s0s s2s1s-s1s0s-s1s0s0s2s" placeholder="YYYY-MM-DD HH:MM:SS" maxlength="19" class="form-control" />
                        </ul>
                    </li>
                    <li>
                        <p>What is the "Date" timestamp of syndey.jpg?</p>
                        <ul class="textbox">
                            <li><input type="text" data-content="70:12:01 02-11-4002" data-question="7s0s:s1s2s:s0s1s   s0s2s-s1s1s-s4s0s0s2s" placeholder="YYYY-MM-DD HH:MM:SS" maxlength="19" class="form-control" />
                        </ul>
                    </li>
                    <li>
                        <p>What is the full file path of DSC07859.jpg inside the web server?</p>
                        <ul class="textbox">
                            <li><input type="text" data-content="GPJ.95870CSD/023/dlroWaeS-70-4002/nadisbeW/" data-question="GsPsJs.s9s5s8s7s0sCsSsDs/s0s2s3s/sdslsrsosWsasesSs-s7s0s-s4s0s0s2s/snsasdsisssbsesWs/s" placeholder="/********/****************/***/********.***" maxlength="43" class="form-control" />
                        </ul>
                    </li>
                    <li>
                        <p>With the information available to you, which city and country were these pictures taken?</p>
                        <ul class="textbox">
                            <li><input type="text" data-content="ailartsuA ,tsaoC dloG" data-question="asislsasrstsssusAs s,stsssasosCs sdslsosGs" placeholder="**** *****, *********" maxlength="21" class="form-control" />
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
</div>
<script type="text/javascript">$(function(){
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
                if (self.find('input[type="radio"][data-content="1"]:checked').length == 1) {
                    correct += 1;
                } else {
                    self.addClass('text-danger');
                }
            }
            // Textbox Question.
            if(self.hasClass('textbox')) {
                var textbox = self.find('input[type="text"]');
                var correct_text = String(textbox.data("content")).trim().split("").reverse().join("");
                if(String(textbox.val()).trim().toLowerCase()==correct_text.toLowerCase()) {
                    correct += 1;
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
</script>