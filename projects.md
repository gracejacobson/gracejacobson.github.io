---
title: /projects
layout: page
permalink: /projects/
---

# BME160: Research Programming <br>
----------

Projects from this course include analyzing DNA sequences for the largest ORF, computing protein properties, and calculating bond lengths and angles. You can access all the projects in the repo [here](https://github.com/gracejacobson/UCSC_BME160/).

<br /><br />Some code from Lab 4, genomeAnalyzer.py:
{% highlight python %}
def main ():
    """Calls FastAreader and NucParams, prints output"""
    myReader = FastAreader()
    myNuc = NucParams()
    for head, seq in myReader.readFasta() :
        myNuc.addSequence(seq)
    
    #print sequence length
    nucCount = (myNuc.nucCount()) / 1000000 #convert to Mb
    print("sequence length = {0:.2f} Mb".format(nucCount)) #prints with 2 decimals
    
    #print GC content
    GCcontent = ((myNuc.nucComp['G']+ myNuc.nucComp['C']) / (myNuc.nucCount())) * 100 #calculates percentage of G and C by getting value from nucComp dict
    print('\nGC content = {0:.1f}%\n '.format(GCcontent)) #prints GC content
     
    #sort and print codons in alphabetical order by amino acid
    for aa in sorted(myNuc.rnaCount.keys()):
        denom = sum(myNuc.rnaCount[aa].values()) #creates denominator for division for relative frequency of codon for amino acid
        for codon in sorted(myNuc.rnaCount[aa].keys()):
            if denom == 0:
                val = 0 #avoids division by zero and creating error
            else:
                val = myNuc.rnaCount[aa][codon] / denom #finds relative frequency of codon for an amino acid
            print ('{:s} : {:s} {:5.1f} ({:6d})'.format(codon, aa, val*100, myNuc.rnaCount[aa][codon]))
{% endhighlight %}

## HTML/CSS/JavaScript <br>
----------

I'm working on using HTML, CSS, and JavaScript in one HTML file for biological applications. One of my projects identifies sequence liabilities in antibodies. You can preview it [here](http://htmlpreview.github.io/?https://github.com/gracejacobson/HTML-CSS-Java/blob/main/AbLiabilities.html).

<br /><br />Here is the main function in JavaScript:
{% highlight javascript %}
function main(){
    list = document.getElementById('selectlist')
    selected = [...list.selectedOptions].map(option => option.value);

    if (document.getElementById("checkbox").checked == true){
        sequence =  document.getElementById("DNAsequence").value
        sequence = sequence.toUpperCase()
        aa = translate(sequence)
        document.getElementById("AA").innerHTML = "<h4> Amino Acid Sequence:</h4> <p>" + aa + "</p>"
        liabilities = getLiabilities(aa, selected)
        document.getElementById("liabilities").innerHTML = "<h4> Liabilities: </h4>"
        document.getElementById("outputlist").innerHTML = liabilities  
    }
    else{
        aa= document.getElementById("DNAsequence").value
        aa = aa.toUpperCase()
        liabilities = getLiabilities(aa, selected)
        document.getElementById("liabilities").innerHTML = "<h4> Liabilities: </h4>"
        document.getElementById("outputlist").innerHTML = liabilities
    }
    }
{% endhighlight %}

