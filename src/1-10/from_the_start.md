<h1 id="h-tip"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/raw/refs/heads/gh-pages/pcaps/1-10/from_the_start.pcap">From The Start <u>🠇</u></h1>
<sup>^^ download me</sup>
> [!TIP]  
> Press the ENTER key to quickly submit answers.

<div class="container">
    <div class="form-row">
        <div class="container">
            <hr>
            <ol>
                <li>
                    <p>How many packets are in the pcap?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="742" data-question="7s4s2s" placeholder="***" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Identify protocols that appear in the pcap. <em>Select all that apply</em></p>
                    <ul class="checklist">
                        <li><label><input type="checkbox" data-question="0" data-content="1" /> TCP</label></li>
                        <li><label><input type="checkbox" data-question="1" data-content="0" /> FTP</label></li>
                        <li><label><input type="checkbox" data-question="1" data-content="0" /> HTTPS</label></li>
                        <li><label><input type="checkbox" data-question="0" data-content="1" /> NTP</label></li>
                        <li><label><input type="checkbox" data-question="1" data-content="0" /> SSL</label></li>
                        <li><label><input type="checkbox" data-question="0" data-content="1" /> ARP</label></li>
                    </ul>
                </li>
                <li>
                    <p>Find the DNS server within the 192.168.100.* network.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="2.001.861.291" data-question="2s.s0s0s1s.s8s6s1s.s2s9s1s" placeholder="***.***.***.*" maxlength="13" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>The DNS server replied with an A record. It contained an IP of 216.58.206.46. What is that A record's name?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="1" data-content="0" /> 8.100.168.192.in-addr.arpa</label></li>
                        <li><label><input type="radio" data-question="0" data-content="1" /> google.com</label></li>
                        <li><label><input type="radio" data-question="1" data-content="0" /> debian.local</label></li>
                        <li><label><input type="radio" data-question="1" data-content="0" /> dnslookup.com</label></li>
                    </ul>
                </li>
                <li>
                    <p>What's the month, day, and year that this pcap was captured?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="81-90-5202" data-question="8s1s-s9s0s-s5s2s0s2s" placeholder="YYYY-MM-DD" maxlength="10" class="form-control" />
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