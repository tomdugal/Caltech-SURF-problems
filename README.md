# Caltech-SURF-problems

Problem 1: Plasmid annotation and WTH?

The control and test plasmids are 5328bp and 5368bp in length (circular) respectively. They each consist of a pBr322 cloning vector backbone which makes up base pairs 1-1841 and 5183-5328 in the control plasmid and 1-1841 and 5223-5368 in the test plasmid.

i. What resistance gene and origin of replication is the plasmid carrying? Does it even have an origin of replication? What antibiotics will be used?

Within the pBr322 backbone is an origin or replication (base pairs 16-635 in each) and a bla gene, encoding beta-lactamase which confers resistance to ampicillin. 

Most likely beta-lactamase structure: http://www.rcsb.org/structure/1BTL

As such, the antibiotic ampicillin can used to select for hosts which have taken up this plasmid.

ii. What reporter proteins are being used or expressed? How will I measure the signal?

There are two fluorescence proteins encoded in each of the plasmids. The first is mRFP1 (https://www.ncbi.nlm.nih.gov/protein/1372102483), a red fluorescence protein. This lies from base pairs 3345-3994. The second is sfGFP (https://www.ncbi.nlm.nih.gov/protein/1372102488), a green fluorescence protein. This lies from base pairs 4035-4745 in the control DNA and 4075-4785 in the test DNA.

These reporter proteins are fluorophores with differing excitation and emission maxima. The RFP emission maximum is 583nm and excitation maximum 558nm. A typical GFP has an excitation peak at ~395nm and emission peak at ~509nm. This means that the two proteins can be distinguished and the expression of either/both/none of them detected using fluorescence microscopy.

iii. What inducible promoters are being used and what inducer chemical do I need to run my experiment?

There is a promoter sequence just upstream of the mRFP1 gene (bp 3261-3286):

TTGACA    TAACAAGAT

Also in the plasmids is a lacI generator cassette. This contains biobricks B0034 (http://parts.igem.org/Part:BBa_B0034), a ribosome binding sequence (bp 3043-3054) and C0012 (http://parts.igem.org/Part:BBa_C0012), a coding region for the lacI repressor protein with an LVA degradation tail (bp 1948-3034).

The promoter showed significant homology to the lacI binding sequence:

AATTGTGAGC  GGATAACAATT

This suggests that the promoter is a negative inducible promoter, regularly bound and repressed by lacI but induced in the presence of allolactose which binds lacI and prevents it binding the promoter.

iv. Design primers which will be used to distinguish your plasmids via colony PCR.

Sequence (5'->3')

Forward primer: CTGAAGGTCGTCACTCCACC
Reverse primer: TATTAGGAGCGGCGAAACCC

(https://www.ncbi.nlm.nih.gov/tools/primer-blast/primertool.cgi?ctg_time=1548847000&job_key=wsgdUfNn_s_Z9W7wY5BKwhmLW_A0mEDtNQ, primer pair 1)

Anneal at 68 degrees celsius. 

The sequence of the reverse primer includes significant sections which lie within the insert in the 'test DNA'. As such it will be unable to bind the control DNA plasmid. This insert-specific colony PCR will mean that product will only be seen from the test DNA with the insert giving a clear 'yes or no' test to distinguish them.

v. Use the annotated plasmid map to figure out what you are studying or testing.

The control and test plasmids, both based upon a pBR322 cloning vector backbone, are identical in sequence other than a sequence insert in the test plasmid at base pairs 4002-4041. Within this insert (bp 4008-4035) is a stem-loop terminator sequence. 

This suggests that the purpose of the study is to determine whether the insertion of this stem-loop terminator prevents expression of the sfGFP from the promoter at bp 3261-3286. 

Therefore:

-Uptake of plasmids by host cells are detected by conferred ampicillin resistance.

-Transformed host cells can be grown on medium carrying allolactose to allow negative induction of the promoter through allolactose binding its repressor lacI.

-The cells can then be observed using fluorescence microscopy at a range of wavelengths.

-Levels of excitation of any fluorophores can be detected over the range of wavelengths and, given the differing excitation and emission maxima of sfGRP and mRFP1, their presence or absence in the cells can be concluded by plotting the results.

-It would be expected that excitation representative of both sfGFP and mRFP1 would be recorded in the control plasmid, since there is no termination sequence preventing continued transcription/translation from the promoter, but only excitation representative of mRFP1 in the test plasmid, since the terminator stem-loop sequence should prevent progression to the sfGFP orf. 
