<h1 id="h-important"><a href="https://media.defcon.org/DEF%20CON%2017/DEF%20CON%2017%20ctf/DEF%20CON%2017%20-%20CTF%20BinJitsu%20-%20Capture%20the%20Flag%20complete%20packet%20capture.rar">Gold Digger</h1></a>

> [!important]
> Do these commands when you get the .rar file:  
> (Go to the directory of the downloaded file)  
> 
```
mkdir dc17 dc17/foo
cd dc17/foo
unrar x ../../DEF\ CON\ 17\ -\ CTF\ BinJitsu\ -\ Capture\ the\ Flag\ complete\ packet\ capture.rar
mergecap -w ../dc17.pcap *  
cd ..
```

Your file is named `dc17.pcap`  

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p>How many unique connections occurred?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="9490082" data-question="9s4s9s0s0s8s2s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many ICMP connections occurred?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="7543" data-question="7s5s4s3s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the year, month, day of the last packet captured?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="20-80-9002" placeholder="YYYY-MM-DD" data-question="2s0s-s8s0s-s9s0s0s2s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the total amount of packets captured?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="24349983" data-question="2s4s3s4s9s9s8s3s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-caution">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            Don't use big tools on this pcap
        </p>
        <p>
            Use capinfos and one of its arguments.
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="5">
                <li>
                    <p>Identify the IP address of the FTP server.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="01.9.13.01" data-question="0s1s.s9s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-tip">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            Carving
        </p>
        <p>
            Some tools are much slower at carving.
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="6">
                <li>
                    <p>How many users can be observed successfully logging into the FTP server?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="3" data-question="3s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which IP address initiated the most connections to the FTP server?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="2.8.13.01" data-question="2s.s8s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which FTP user retrieved the FTP file "deltaw"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="suomynona" data-question="ssusosmsysnsosnsas" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the MD5 hash of "deltaw'?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="43cc9f247efccd08335c98f81ca0b073" data-question="4s3scscs9sfs2s4s7sesfscscsds0s8s3s3s5scs9s8sfs8s1scsas0sbs0s7s3s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What type of executable is "deltaw"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="fle" data-question="fslses" placeholder="***" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-tip">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            tip
        </p>
        <p>
            Use the command "file"
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="11">
                <li>
                    <p>What is the SHA1 hash of "key_save.txt"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="8fd73abe5a0b5c228246820444fca1b3a1edd64d" data-question="8sfsds7s3sasbses5sas0sbs5scs2s2s8s2s4s6s8s2s0s4s4s4sfscsas1sbs3sas1sesdsds6s4sds" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the password shown in plaintext that was used to login to FTP user "anonymous"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="@ptfl" data-question="@spstsfsls" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the web server's software name and version located in 10.31.9.10?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="22.4.1/dptthgil" data-question="2s2s.s4s.s1s/sdspststshsgsisls" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Identify the IP address that used the user agent "curl/7.18.0".</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="991.7.13.01" data-question="9s9s1s.s7s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Enter the TCP data stream found from the connection using user agent "curl/7.18.0".</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="0885919421" placeholder="**********" data-question="0s8s8s5s9s1s9s4s2s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many HTTP servers have a hostname that contains the string "team"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="6" data-question="6s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>From these "team" HTTP servers, how many GET requests returned successful?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="1" data-question="1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which IP address conducted nmap scans on 10.31.1.2 using nmap's default user-agent?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="9.01.13.01" data-question="9s.s0s1s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many UDP connections occurred between 10.31.1.2 and the machine that nmap scanned?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="5" data-question="5s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which TCP port from 10.31.1.2 was contacted the most by the machine that nmap scanned?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="9008" data-question="9s0s0s8s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique IP addresses belong to the 10.31.9.0/24 subnet?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="41" data-question="4s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many connections occurred on destination port 25?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="061" data-question="0s6s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many connections occurred on destination port SMTP but isn't actually SMTP traffic?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="951" data-question="9s5s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Identify the IP address of the SMTP server.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="2.1.13.01" data-question="2s.s1s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the most used TCP port by number of connections?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="3434" data-question="3s4s3s4s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the least used IP address by number of connections?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="211.3.13.01" data-question="2s1s1s.s3s.s1s3s.s0s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique files were attempted to be retrieved with a GET request?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="105" data-question="1s0s5s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique files are actually real because the HTTP server returned a successful response?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="392" data-question="3s9s2s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many files present end with the .txt file extension?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="1" data-question="1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique IP addresses belong to the private class A network?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="041" data-question="0s4s1s" class="form-control" />
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